---
title: ArtOfTest.Runner
page_title: ArtOfTest.Runner
description: "Test Studio Command line runner client is called ArtOfTest.Runner. Test Studio execution engine in the command prompt"
previous_url: /user-guide/test-runners/artoftestrunner.aspx, /user-guide/test-runners/artoftestrunner, /user-guide/command-line-test-execution/artoftestrunner.aspx, /user-guide/command-line-test-execution/artoftestrunner
position: 1
---
# ArtOfTest.Runner

The ArtOfTest.Runner.exe is installed in your <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> installation directory. The default location is:

- **C:\Program Files (x86)\Telerik\Test Studio\Bin**

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

When working with the execution engine in the command prompt always make sure you have started it as Administrator and have the root directory in context as shown below so that you can call the runner directly.

![cmd][1]

## Options

Here is the Help Screen for ArtOfTest.Runner.exe:

![Options][2]

## Execution Options

Execution options modify command line test execution behavior. The help screen (displayed by inputting ArtOfTest.Runner.exe -help from the command line) provides a brief explanation of each option. Here are some further notes about specific options.

Several execution options use file paths as values. Keep in mind the following notes when using file paths in the command prompt:

- Enclose the file path in double quotes.
- To prevent typing mistakes, use the clipboard paste option within the command prompt window. To find the paste option after copying the path to the clipboard, right mouse click on the top left corner of the command prompt and choose **Edit > Paste**.

![Edit>Paste][3]

-The **test** option takes the full path to an individual test file with the **.tstest** file extension. This file will be located in your main project directory and under any folder structure you have created to organize your tests. You can use the **test** option by itself. By default results will be stored in the **Results** folder under the project’s root directory.

<table id="no-table">
<tr>
<td>![Test Execution Syntax][4]<br>ArtOfTest.Runner Test Execution syntax</td>
</tr>
<tr>
<td>![Test Execution Result][5]<br>ArtOfTest.Runner Test Execution result</td>
</tr>
<table>

-The **list** option takes the full path to a test list file with the **.aiilist** file extension. This option  will execute a test list which has multiple tests included. All test lists for your project can be found in the test list folder under your project root folder. You can use the test option by itself. By default results will be stored in the **Results** folder under the project’s root directory. For more information about test lists, see <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">Test Lists</a>. 

<table id="no-table">
<tr>
<td>![Test List Execution Syntax][6]<br>ArtOfTest.Runner Test List Execution syntax</td>
</tr>
<tr>
<td>![Test List Execution Result][7]<br>ArtOfTest.Runner Test List Execution result</td>
</tr>
<table>

-The **out** option allows choice of an alternative folder to store the results to and takes a full path value to the respective folder.
<br>
-The **result** option allows change of the default result file name and takes file name (including the file extension and in double quotes).
<br>
-If any of the **xml** or **html** options are used the respective alternative result file will be stored to the default location if an output folder is not specified.
<br>
-If any of the **junit** or **junitstep** options is used a JUnit xml result file will be generated. The difference will be respectively whether to convert a test or a test step to a junit test.
<br>
-The **PersistOnEachStep** option could be set to true in case explicitly the results are required. This option will save the results after each executed step.
<br>
-The **settings** option takes the full path to a JSON file containing custom settings for the run.

Below is an example of a complete JSON setting file that contains all of Telerik's test/test list run configuration settings. These are corresponding to the available <a href="/getting-started/test-execution/test-list-settings" target="_blank">test list settings</a>.

```JSON
{
  "Settings": {
    "__type": "ArtOfTest.WebAii.Core.Settings",
    "__value": {
      "Web": {
        "__type": "ArtOfTest.WebAii.Core.Settings+WebSettings",
        "__value": {
          "IsProfilingExecution": false,
          "ExecutingBrowsers": [],
          "UseMultiBrowserExecution": false,
          "RecycleBrowser": true,
          "AspNetDevServerPort": -1,
          "LocalWebServer": 0,
          "EnableUILessRequestViewing": false,
          "WebAppPhysicalPath": "",
          "DefaultBrowser": 2,
          "EnableScriptLogging": false,
          "BaseUrl": "http://at-hyperv01:85",
          "KillBrowserProcessOnClose": false,
          "AutoCalibrateBrowsers": false,
          "UseHttpProxy": false,
          "EnableSilverlight": false,
          "VerboseHttpProxy": false,
          "SilverlightConnectTimeout": 60000,
          "SilverlightApplicationPath": null
        }
      },
      "Wpf": {
        "__type": "ArtOfTest.WebAii.Core.Settings+WpfSettings",
        "__value": {
          "DefaultApplicationPath": null
        }
      },
      "CreateLogFile": true,
      "LogLocation": "C:\\\\WebAiiLog\\\\",
      "QueryEventLogErrorsOnExit": false,
      "LogAnnotations": true,
      "SimulatedMouseMoveSpeed": 0.3,
      "ExecuteInDevelopmentTests": false,
      "WaitCheckInterval": 500,
      "ElementWaitTimeout": 15000,
      "ExecuteCommandTimeout": 1000,
      "ExecutionDelay": 0,
      "UnexpectedDialogAction": 2,
      "AnnotateExecution": false,
      "AnnotationMode": 0,
      "XMultiMgr": true,
      "ClientReadyTimeout": 15000,
      "DisableDialogMonitoring": false,
      "RunnerResponseTimeout": 0.0
    }
  },
  "WebSettings": null,
  "PropertyBag": null
}

```

## Publish Results To TFS

**Note:** All options listed in the help screen in relation to results publishing to TFS are mandatory. Below are some additional notes to each of the options. 

- The **server** option takes the TFS server name with its full path in double quotes like this *"http://myTFS.myDomain.com:8080/tfs"*.
- The **build** option takes the respective build which the results could be associated to. 
- The **project** option takes the name of the current team project which the build belongs to. 
- The **platform** option takes the respective platform which is usually Windows and thus the option takes value "win".
- The **flavor** defines if the build is Debug or Release (defaults to "Debug"). 

Below is a sample command to publish results to TFS from a test list execution. 

![Publish Results to TFS][8]

## Exit Codes

ArtOfTest.Runner returns an exit code so the Build Server can check for it on process exit in case of an exception:


<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
}
table.docs th {
color:#fff;
background-color:#00аб8е;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>
<table class="docs">
<tr>
	<th>Code</th><th>Title</th><th>Summary</th>
</tr>
<tr>
	<td>**0**</td><td>RUN_TESTS_SUCCESS </td><td>Run is processed and all tests passed.</td>
</tr>
<tr>
	<td>**1**</td><td>RUN_TESTS_ERROR</td><td>Run is processed and some tests failed.</td>
</tr>
<tr>
	<td>**2**</td><td>NOT_RUN_UNEXPECTED_ERROR</td><td>Run is not processed due to unexpected error.</td>
</tr>
<tr>
	<td>**3**</td><td>NOT_RUN_COMPILATION_ERROR</td><td>Run is not processed due to compilation errors.</td>
</tr>
<tr>
	<td>**10**</td><td>NOT_RUN_USAGE_INFO</td><td>No run to process, requested usage info.</td>
</tr>
<tr>
	<td>**11**</td><td>NOT_RUN_INVALID_COMMAND_ARGS</td><td>No run to process due to general invalid arguments error.</td>
</tr>
<tr>
	<td>**12**</td><td>NOT_RUN_TEST_NOT_FOUND</td><td>Run is not processed due to invalid test path argument.</td>
</tr>
<tr>
	<td>**13**</td><td>NOT_RUN_TESTLIST_NOT_FOUND</td><td>Run is not processed due to invalid test list path argument.</td>
</tr>
<table>


[1]: /img/features/test-runners/artoftest-runner/fig1.png
[2]: /img/features/test-runners/artoftest-runner/fig2.png
[3]: /img/features/test-runners/artoftest-runner/fig3.png
[4]: /img/features/test-runners/artoftest-runner/fig4.png
[5]: /img/features/test-runners/artoftest-runner/fig5.png
[6]: /img/features/test-runners/artoftest-runner/fig6.png
[7]: /img/features/test-runners/artoftest-runner/fig7.png
[8]: /img/features/test-runners/artoftest-runner/fig8.png