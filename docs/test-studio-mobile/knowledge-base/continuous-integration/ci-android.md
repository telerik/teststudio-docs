---
title: Android
page_title: Android CI
description: "Setup CI build for Android apps using Mobile Testing Runner CLI"
publish: true
position: 0
slug: ms-ci-android
previous_url: /test-studio-mobile/knowledge-base-mb/continuous-integration-mb/ci-android,/test-studio-mobile/knowledge-base-mb/continuous-integration-mb
---

#Setup CI build for Android apps using Mobile Testing Runner CLI

This topic is dedicated to the steps that can be followed to create a Jenkins CI build based on the Mobile Testing Runner CLI. Requirements:

*	[Jenkins Server](http://jenkins-ci.org/)
*	Android SDK
*	Download and unzip on your local machine [Mobile Runtime package]({% slug ms-download%}#4-Mobile-Runtime) for the OS you are running. This demo uses the Windows package.
*	Download and install [Mono](http://www.mono-project.com/download/) (only if you want to run on Mac/Linux) 
*	Powershell (optional - used in this demo)
*	GitHub/TFS/Git Jenkins plugin
*	Post-build Actions Jenkins plugin (recommended)

##Setup Jenkins build:

1.&nbsp; Download and install Jenkins on the Windows machine. Install the Jenkins plugins afterwards.

2.&nbsp; Open the Jenkins Web UI and create a new Jenkins job.

> As of release **R1 2018 (v2018.1.130)** you could install and use the <a href="/test-studio-mobile/knowledge-base/continuous-integration/jenkins-ci-plugin-mobile" target="_blank">Jenkins Mobile Studio Plugin</a>.

3.&nbsp; In the **Source Code Management** section, connect to the repository where your tests reside. We will use a Github repository for this demo.

  ![jenkins setup](/img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/android/fig1.png)

4.&nbsp; Setup the Windows batch command that will execute the tests. Here, a powershell script module function is used.

  ![batch command](/img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/android/fig2.png)

The actual script code follows. For brevity, it implements 4 functions that are responsible for different tasks. Note the describing comments in the code.

```
$ErrorActionPreference = "Stop"
	# Starts the Emulator.
      function start-emulator {
        # Start an android Emulator.
        emulator -avd Emulator51

        # Wait 2 minutes for the Emulator to load up. Adjust this time depending on the emulator version.
        start-sleep -s 120

        # Call the function that installs the app to test and connects the agent to the message server.
        install-connect-apps
      }

      # Installs the app and connects the agent to the message server which must be started first.
      function install-connect-apps {
        # Install the app to test. Change the path to a local store (where you have build the project) or online repository.
        adb -s emulator-5554 install -r "Android\Apps\DemoApplicationTesting.apk"
        start-sleep -s 10

        # Start the Mobile Testing agent app.
        adb -s emulator-5554 shell monkey -p com.telerik.testing.executionagent -c android.intent.category.LAUNCHER 1
        start-sleep -s 10

        # Set the location to the Message Server folder (where you have downloaded and unziped it) and start the message server on port 8081.
        Set-Location -Path (".\MobileRuntime-Windows\MessageServer")
        start-process msgsrv-ctl.bat "stop"
        start-sleep -s 5
        start-process msgsrv-ctl.bat "start 8081"
        start-sleep -s 5

        # Connect the Mobile Testing agent to the message server.
        adb -s emulator-5554 forward tcp:8082 tcp:8082
        start-sleep -s 10
        node.exe tmtest.js connect --message-server-url ws://localhost:8081 --address localhost:8082
        start-sleep -s 10

        # Call the function that runs the tests.
        run-tests

        # Stop the Message Server
        start-process msgsrv-ctl.bat "stop"
      }

      # Runs the tests.
      function run-tests{
        # Set the location of the MobileRuntime folder (where you have downloaded and unziped it) and execute a run.
        Set-Location -Path (".\MobileRuntime-Windows")

        # Run the tests and output results to a json file.
        .\Telerik.MobileTesting.Runner.exe /msgServer=ws://localhost:8081 /project=C:\[userName]\MyTestProjectName 
		/list=C:\[userName]\MyTestProjectName\TestLists\ListName.mtlist 
		/output=C:\OutputResultsFolder\Results.mtresult /resultType=1
        start-sleep -s 10 

        # If a test fails, stop the Emulator and exit the build with error code.
        If($LASTEXITCODE -ne 0)
        {
          stop-emulator
          exit 1
        }
        start-sleep -s 10
        # Call the function that stops the emulator.
        stop-emulator
      }

      # Stops the emulator.
      function stop-emulator{
        $processes = @(Get-Process emulator-arm -ErrorAction SilentlyContinue)
        foreach ($process in $processes)
        {
          $process | Stop-Process -force
        }
      }

      export-modulemember -function start-emulator

```

The **start-emulator** function just launches the Android emulator named *Emulator51*. The emulator must be created prior to running the script. [Android AVD](http://developer.android.com/tools/devices/managing-avds.html) can be used for this task.

After the emulator is started, the next function in the chain is called. The **install-connect-apps** function does 3 tasks:

>Before **install-connect-apps** function is called the Mobile Testing Agent app must be [installed]({% slug ms-install-agent-app%}) and the testable аpp must be [configured for testing]({% slug ms-configure-android%}) and available for deployment as built .apk file.

*	Installs the testable App on the launched emulator. This app must be instrumented with the Test Studio Mobile extension and built as described [here]({% slug ms-configure-android%}).

*	Starts the Mobile Testing agent app on the emulator.

*	Connects the Mobile Testing Аgent app to the message server. Since message server is started on port 8081, we use 8082 for the connection. Note that this is the default port for Mobile Testing Agent app USB connection and if you want to use another port, you will have to change it both in the script and in the Mobile Testing Agent app [USB settings]({% slug ms-connect-agent-usb%}).

The **run-tests** function navigates to a location where test project is stored and then calls a command that executes its tests on the emulator against the testable app. If a test fails the emulator is closed and the build is marked as failed.

The last function **stop-emulator** just closes the emulator no matter whether the build passes or fails.

Jenkins also supports emailing build results and build artifacts. Setting up these post-build actions, ensures that the build status (pass or fail) and the actual test results are delivered to the responsible people.

Add a post build action - to publish JUnit test results report. This will provide results to be visible from Jenkins UI.

**See Also**

*	[Continuous Integration iOS]({% slug ms-ci-ios%})