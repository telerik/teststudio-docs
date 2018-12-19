---
title: Mobile Testing Test Runner CLI
page_title: Mobile Testing Test Runner CLI
description: Mobile Testing Test Runner CLI
slug: ms-test-runner
tags: test, explorer, mobile
publish: true
position: 9
previous_url: /test-studio-mobile/getting-started-mb/mobile-testing-runner-cli,/test-studio-mobile/knowledge-base/continuous-integration/cli
---
#Mobile Testing Test Runner CLI

The Mobile Testing Test Runner Command Line Interface provides granular control over executing your tests. It runs on Windows, Linux and Mac machines and can be used for test execution only.
* On Windows 7+ machines, Mobile Testing Runner CLI installs as part of Test Studio Mobile and its default location is in *%TestStudioInstallationFodler%\Bin\MobileStudio*. It can also be downloaded and run separately as part of the [Mobile Runtime]({% slug ms-download%}#4-Mobile-Runtime).
* On Mac and Linux machines, Mobile Testing Runner CLI can be downloaded and run separately as part of the [Mobile Runtime]({% slug ms-download%}#4-Mobile-Runtime). ([Mono][1] is required to be installed on the machine).

Mobile testing runner CLI is an executable file that uses the following format:

Windows:

**Telerik.MobileTesting.Runner.exe** [/msgServer=message_server] [/project=project_root]
\[(/test=test.mttest) | (/list=list.mtlist)] (/deviceId=device_id) (/runName=run_name)
(/output=output.mtresult)

Mac/Linux:

**mono Telerik.MobileTesting.Runner.exe** [/msgServer=message_server] [/project=project_root]
\[(/test=test.mttest) | (/list=list.mtlist)] (/deviceId=device_id) (/runName=run_name)
(/output=output.mtresult)

Where:
* Square brackets mean the command-line argument is mandatory. 
* Parenthesis mean the argument is optional. 
* The “|” means “OR” meaning /test OR /list can be used. 

The tool accepts the following the command-line arguments:

* `/msgServer=message_server`

	The address of a running [message server]({% slug ms-message-server%}) to which the test device(s) are connected to. 

	> A message server is running every time you open a Test Studio Mobile project and its host and port can be found in the [project settings dialog]({% slug ms-project-settings%}). A [stand-alone version]({% slug ms-message-server%}#Standalone-Execution) of the message server can also be run without using the Test Studio GUI.

* `/project=project_root`

	Project_root is the full path to the root folder of a project which tests or lists will be executed.

	> The test project root is the folder that contains the `settings.mt` file.

* `/listDevices=fullInfo or /listDevices=onlyId`

	List all connected devices' info - full info or only id.


* `/test=test.mttest`

	Full or relative path to the test.mtest that the runner will execute, the relative path is relative to the project root provided in the /project argument. 

	> The `/test` argument cannot be used in the same command with `/list` argument.

* `/list=list.mtlist`

	Full or relative path to the list.mtlist that the runner will execute, the relative path is relative to the TestLists folder of the project root (provided in the /project argument) . Test list is a collection of single tests that resides in the \TestLists folder of a mobile testing project. 

	> The `/list` argument cannot be used in the same command with `/test` argument. By default if the `/output` argument is not set, a result file containing the test list execution results is created in the `\Results` folder of the test project.

* `/deviceId=device_id`

	This is an optional argument which will make the runner execute the test or list only on devices specified by their device_id.  

	By default a test or list will automatically execute on the first valid device connected to the message server. The device id of a connected device can be found in the **Connected Devices** pane in the Test Studio Mobile or by using the `getagents` command of the `tmtest` tool. This tool is located in the `MessageServer` folder and can be used as follows:

	1. Open a command window and navigate to the `MessageServer` folder. If you have TestStudio installed, this folder is located in *%TestStudioInstallationFodler%\Bin\MobileStudio*. If you use the [Mobile Runtime]({% slug ms-download%}#4-Mobile-Runtime), the folder is located in the root of the runtime folder.

	2. Type **node tmtest getagents -h** or **node tmtest getagents --help** to see options.

	3. Type **node tmtest getagents** to see a list of agents connected to the default message server URL at ws://localhost:8081 or specify `--message-server-url` argument if your message server runs on port different than 8081.

	**iOS**

	![ios](/img/test-studio-mobile/getting-started-mb/mobile-testing-runner-cli/fig1.png)

	**Windows**

	![Windows](/img/test-studio-mobile/getting-started-mb/mobile-testing-runner-cli/fig2.png)

* `/runName=run_name`

	Set a custom test run name for the result.

* `/output=output.mtresult`

	Provide a full path to a specific output location.

* `/resultType=result_type`

	Results format:<br>
	0 - Mobile Studio Json results file (default)<br>
	1 - JUnit XML (test to JUnit test)<br>
	2 - JUnit XML (test step to JUnit test)<br>

	> The default result is in JSON format saved in a file having `.mtresult` extension. It can be loaded in [Test Studio Mobile results view]({% slug ms-testlist-execution%}#results) if the result is saved in the `{pathToYourProject}\Results` folder of a test project. 
	>If the `/output` argument is not set, the result is saved in the `{pathToYourProject}\Results folder` despite of its type.
	

**Examples:**

Below are several examples of running Telerik.MobileTesting.Runner.exe via the command line.

> The sample command lines below may split into two or more lines. This is a visual effect that depends on the width of the help viewer’s window. When specifying a command line for mobile testing runner, type all command-line arguments into the same line.

The following command will connect to a running message server and execute a single test on the first valid device connected to the message server.

	"C:\Program Files (x86)\Telerik\Test Studio\Bin\MobileStudio\Telerik.MobileTesting.Runner.exe" /msgServer=ws://localhost:8084 /project="c:\testproject\MobileDemoProject" /test=androidTest.tmtest

The following command will run a test list against a specific device (its device id provided as argument) and output the result at a specified location.

	"C:\Program Files (x86)\Telerik\Test Studio\Bin\MobileStudio\Telerik.MobileTesting.Runner.exe" /msgServer=ws://localhost:8084 /project="c:\testproject\MobileDemoProject" /deviceId= 6968cda2-83e6-4e39-9fcf-30b614656229 /list=AllAndroidTests.mtlist /output="c:\mobileTestingResults\androidRun.mtresult"

The following command will run a test list on the first valid device connected to the message server, create a result file from the run and put a custom test run name in the result file.

	"C:\Program Files (x86)\Telerik\Test Studio\Bin\MobileStudio\Telerik.MobileTesting.Runner.exe" /msgServer=ws://localhost:8084 /project="c:\testproject\MobileDemoProject" /list=AllAndroidTests.mtlist  /runName=AndroidListIteration1   /ouput="c:\mobileTestingResults\androidSingleTestRun.mtresult"


> Please note that as of version **2017 R3** the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

[1]: http://www.mono-project.com/download/

See Also
--------

* [Downloads]({% slug ms-download%})
* [System Requirements]({% slug ms-requirements%})