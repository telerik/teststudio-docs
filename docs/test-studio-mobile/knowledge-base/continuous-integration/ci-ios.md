---
title: iOS
page_title: iOS CI
description: "Setup CI build for iOS apps using Mobile Testing Runner CLI"
publish: true
position: 0
slug: ms-ci-ios
previous_url: /test-studio-mobile/knowledge-base-mb/continuous-integration-mb/ci-ios
---

#Setup CI build for iOS apps using Mobile Testing Runner CLI

This topic is dedicated to the steps that can be followed to create a Jenkins CI build based on the Mobile Testing Runner CLI. Requirements:

* [Jenkins Server](http://jenkins-ci.org/)
* Mac OS x 9+
* Xcode 6+
* iOS SDK
* Download and unzip on your local machine [Mobile Runtime package]({% slug ms-download%}#4-Mobile-Runtime) for Mac.
* Download and install [Mono](http://www.mono-project.com/download/)
* GitHub/TFS/Git Jenkins plugin
* Post-build Actions Jenkins plugin (recommended)

##Setup Jenkins build:

1.&nbsp; Download and install Jenkins on the Mac machine. Install the Jenkins plugins afterwards.

2.&nbsp; Open the Jenkins Web UI and create a new Jenkins job.

> As of release **R1 2018 (v2018.1.130)** you could install and use the <a href="/test-studio-mobile/knowledge-base/continuous-integration/jenkins-ci-plugin-mobile" target="_blank">Jenkins Mobile Studio Plugin</a>.

3.&nbsp; In the **Source Code Management** section, connect to the repository where your tests reside. We will use a Github repository for this demo.

  ![jenkins setup](/img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/ios/fig1.png)

4.&nbsp; Add an Execute Shell build step.

  ![build](/img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/ios/fig2.png)

  In this step add a short script that will start a simulator, install apps in it and execute tests. Note the describing comments in the code.

  > Before the script bellow is called the Mobile Testing Agent app must be [installed]({% slug ms-install-agent-app%}) and the testable аpp must be [configured for testing]({% slug ms-configure-ios%}) and available for deployment as built .app file.


  ```
    export PATH=$PATH:/usr/local/bin

    # sudo `-H -u {ROOT_USER}` this command is used to ensure that every command is executed on the same user. Start the desired simulator by its ID. 
    # You can find a list of available simulators and their IDs by executing `xcrun simctl list`.
    # The `|| return 0` pipe is used in order to escape the common error `timeout waiting for  device to boot` which will always appear on slower machines.
    sudo -H -u {ROOT_USER} open -a Simulator --args -CurrentDeviceUDID {DEVICE_ID} || return 0 
  
    # In order to ensure the simulator is ready, you can add the a sleep step depending on the machine speed.
    sleep 60

    # Install the app to test. Change the path to a local store (where you have build the project) or online repository.
    sudo -H -u {ROOT_USER} xcrun simctl install booted $WORKSPACE/DemoApplicationTesting.app
    sleep 1

    # Launch the Mobile Testing agent on the device
    sudo -H -u {ROOT_USER} xcrun simctl launch booted com.telerik.MobileTesting

    # Set the location to the Message Server folder (where you have downloaded and unziped it) and start the message server on port 8081.
    cd "/MobileRuntime-Mac/MessageServer/"
    sudo -u {ROOT_USER} ./msgsrv-ctl.sh stop
    sleep 10
    sudo -u {ROOT_USER} ./msgsrv-ctl.sh start 8081
    sleep 10

    # Connect the Mobile Testing agent to the message server.
    sudo -u {ROOT_USER} ./node tmtest.js connect --message-server-url "ws://127.0.0.1:8081" --address "localhost:8082"

    # Navigate to the MobileRuntime folder (where you have downloaded and unziped it) and execute a run.
    cd "/MobileRuntime-Mac/"
    sudo -u {ROOT_USER} mono Telerik.MobileTesting.Runner.exe /msgServer="ws://127.0.0.1:8081" /project="/Users/MyTestProjectName" /list="/Users/MyTestProjectName/TestLists/MyListName.mtlist" /resultType=1

    #Stop message server
    cd /Users/testing/Desktop/jenkins/workspace/CI\ -\ iOSRunner\ -\ Develop/MessageServer
    sudo -u testing ./msgsrv-ctl.sh stop
  ```

5.&nbsp; Add Post-Build action step. Those are steps which will be run after the test execution.

In this step, make sure that the simulator will reset to its original state:

```
    # Shut down the desired simulator by its ID
    sudo -H -u {ROOT_USER} xcrun simctl shutdown {DEVICE_ID}
    sleep 10

    # The next command is optional, it will reset the simulator and everything on it which means that next time in addition to the app under test, the Mobile Testing agent should be installed again.
    sudo -H -u {ROOT_USER}  xcrun simctl erase {DEVICE_ID}
    sleep 10

    # Kill simulator process
    sudo -u {ROOT_USER} killall "Simulator" {DEVICE_ID}

```

Jenkins also supports emailing build results and build artifacts. Setting up these post-build actions, ensures that the build status (pass or fail) and the actual test results are delivered to the responsible people.

**See Also**

* [Continuous Integration Android]({% slug ms-ci-android%})