---
title: Command Line Runner 
page_title: Command Line Runner - Test Studio Dev Documentation
description: Command Line Runner for Test Studio Dev tests
position: 10
---
# Command Line Runner

The ArtOfTest.Runner.exe is the command line runner for __Test Studio Dev__ tests and is installed in the Bin folder under the installation directory of the product. The default location is:

- **C:\Program Files (x86)\Progress\Test Studio**

When working with the execution engine in the command prompt always make sure you have started it as Administrator and have the root directory in context as shown below so that you can call the runner directly.

![cmd][1]

## Help Screen

Here is the Help Screen for ArtOfTest.Runner.exe:

![Options][2]

## Execution Options

Execution options modify command line test execution behavior. The help screen (displayed by inputting ArtOfTest.Runner.exe -help from the command line) provides a brief explanation of each option. Here are some further notes about specific options.

Several execution options use file paths as values. When using file paths in the command prompt:

- Enclose the file path in double quotes.
- To prevent typing mistakes, use the clipboard paste option within the command prompt window. To find the paste option after copying the path to the clipboard, right mouse click on the top left corner of the command prompt and choose **Edit > Paste**.

![Edit>Paste][3]

### File to Execute Options

- The **test** option takes the full path to an individual test file with the **.tstest** file extension. This file will be located in your main project directory and under any folder structure you have created to organize your tests. You can use the **test** option by itself. By default results will be stored in the **Results** folder under the project’s root directory.

<table id="no-table">
<tr>
<td>![Test Execution Syntax][4]<br>ArtOfTest.Runner Test Execution syntax</td>
</tr>
<tr>
<td>![Test Execution Result][5]<br>ArtOfTest.Runner Test Execution result</td>
</tr>
<table>

- The **list** option takes the full path to a test list file with the **.aiilist** file extension. This option  will execute a test list which has multiple tests included. All test lists for your project can be found in the test list folder under your Test Studio Dev project root folder. You can use the test option by itself. By default results will be stored in the **Results** folder under the project’s root directory. For more information about test lists in Test Studio Dev, see <a href="/features/test-execution/test-lists-in-vs-2017-2019" target="_blank">Test Lists</a>.

- The **root** option takes full path to the project root folder.

### Results Related Options

- The **out** option allows choice of an alternative folder to store the results to and takes a full path value to the respective folder.

- The **result** option allows change of the default result file name and takes file name (including the file extension and in double quotes).

- If any of the **xml** or **html** options are used the respective alternative result file will be stored to the default location if an output folder is not specified.

- If any of the **junit** or **junitstep** options is used a JUnit xml result file will be generated. The difference will be respectively whether to convert a test or a test step to a junit test.

- The **PersistOnEachStep** option could be set to true in case explicitly the results are required. This option will save the results after each executed step.

### Settings Option

- The **settings** option takes the full path to a settings file with the **.xml** file extension.

Below is an example of a complete JSON setting file that contains all of Telerik's test/test list run configuration settings. These are corresponding to the available <a href="/features/test-execution/test-list-settings" target="_blank">test list settings</a>.

````JSON
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
          "BaseUrl": "http://testedSite.com",
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
	   "ResponsiveWeb": {
		"__type": "ArtOfTest.WebAii.Core.Settings+ResponsiveWeb",
		"__value": {
		  "Width": 414,
		  "Height": 896,
		  "UserAgent": "Mozilla/5.0 (iPhone; CPU iPhone OS 11_0 like Mac OS X) AppleWebKit/604.1. 38 (KHTML, like Gecko) Version/11.0 Mobile/15A356 Safari/604.1"         
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

````

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
<td>
	
**0**</td><td>RUN_TESTS_SUCCESS </td><td>Run is processed and all tests passed.</td>
</tr>
<tr>
<td>
	
**1**</td><td>RUN_TESTS_ERROR</td><td>Run is processed and some tests failed.</td>
</tr>
<tr>
<td>
	
**2**</td><td>NOT_RUN_UNEXPECTED_ERROR</td><td>Run is not processed due to unexpected error.</td>
</tr>
<tr>
<td>
	
**3**</td><td>NOT_RUN_COMPILATION_ERROR</td><td>Run is not processed due to compilation errors.</td>
</tr>
<tr>
<td>
	
**10**</td><td>NOT_RUN_USAGE_INFO</td><td>No run to process, requested usage info.</td>
</tr>
<tr>
<td>
	
**11**</td><td>NOT_RUN_INVALID_COMMAND_ARGS</td><td>No run to process due to general invalid arguments error.</td>
</tr>
<tr>
<td>
	
**12**</td><td>NOT_RUN_TEST_NOT_FOUND</td><td>Run is not processed due to invalid test path argument.</td>
</tr>
<tr>
<td>
	
**13**</td><td>NOT_RUN_TESTLIST_NOT_FOUND</td><td>Run is not processed due to invalid test list path argument.</td>
</tr>
<table>

[1]: images/artoftest-runner/fig1.png
[2]: images/artoftest-runner/fig2.png
[3]: images/artoftest-runner/fig3.png
[4]: images/artoftest-runner/fig4.png
[5]: images/artoftest-runner/fig5.png
