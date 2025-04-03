---
title: ArtOfTest.Runner.exe - Test Studio CLI Runner
page_title: Test Studio CLI Runner "ArtOfTest.Runner.exe"
description: "Test Studio Command line runner client is called ArtOfTest.Runner.exe. Test Studio execution engine in the command prompt"
position: 1
---
# Test Studio CLI Runner ArtOfTest.Runner.exe

The CLI runner __ArtOfTest.Runner.exe__ is deployed with any of the Test Studio editions in the Test Studio installation directory. The default install folder where you can find the runner is __C:\Program Files (x86)\Progress\Test Studio\Bin__.

This article guides you trough the options of the Test Studio CLI Runner for building commands to execute tests. 

- [How to Call the ArtOfTest.Runner.exe in Command Prompt](#how-to-call-the-artoftestrunnerexe-in-command-prompt)
- [Help Screen](#help-screen)
- [Options to Specify Which File to Execute](#options-to-specify-which-file-to-execute)
- [Options to Customize the Results File](#options-to-customize-the-results-file)
- [Option to Use Custom Settings for the Execution](#option-to-use-custom-settings-for-the-execution)

## How to Call the ArtOfTest.Runner.exe in Command Prompt

Similar to any other executable files you have few options to call the ArtOfTest.Runner.exe in the command prompt. 

- Use the full file path to call the *.exe. 
- Change the context root directory in the command prompt window to the one containing the *.exe file and use the *.exe name directly. 
- Set the *.exe directory as environmental variable in the OS and use the *.exe name directly from whichever directory is the current context. 

![cmd][1]

## Help Screen

Use the `help` option to get a list of all options supported by the CLI runner. The short form to use is `/?` or `/h`. Below is the Help Screen for __ArtOfTest.Runner.exe__:

![Help screen shows the list of all options][2]


## Options to Specify Which File to Execute

The __ArtOfTest.Runner.exe__ supports the execution of a single test or a list of tests. Choose the option suitable for your needs. 

### test Option

The `test` option accepts full file path to an individual test with the **\*.tstest** file extension. 

> __Note!__
><br>
> Each Test Studio test is part of a project and it can't exist on its own. This is why __running individual tests requires a project Settings.aiis file__. So, you can __use the `test` option by itself only when the test file is in the project root folder__ where the Settings.aiis file. 
><br>
><br>
> Otherwise, __when the test is nested under any folder in the project use the `test` option in combination with the `root` one__ to specify the associated project root folder where the Settings.aiis file is. 
 
### Example Commands for test Option

- Run individual test stored in the project root folder: 

````cmd
> "C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
test="D:\Test Studio Projects\July2024\demoTest-AOTRunner.tstest"
````

![Run individual test stored in the project root folder][5]

- Run individual test stored in a sub-folder under the project root one: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
test="D:\Test Studio Projects\July2024\inProjectFolder\nestedDemoTest.tstest" 
root="D:\Test Studio Projects\July2024"
````

![Run individual test stored in a sub-folder under the project root one][4]

### list Option

The `list` option takes the full path to a test list file with the **\*.aiilist** file extension. 

> __Note!__
><br>
> Each Test Studio test list is part of a project and it can't exist on its own. Test list files are stored in the __TestLists__ sub-folder under the project root one.
><br>
> The **\*.aiilist** file contains the test list settings applied for it in the Test Studio project, so you can __use the `list` option by itself__.

### Example Commands for list Option

- Run test list: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist"
````

![Run test list][6]

### root Option 

The `root` option takes the full path to the project root folder and is used in combination with either `test`, or `list` options.

## Options to Customize the Results File

By default the result files generated from the CLI runner execution are output in the **Results** sub-folder under the project’s root directory.The __ArtOfTest.Runner.exe__ supports outputting the results from a test/test list run in different formats and saving the file in custom location. 

> __Tip__ 
><br>
> All result related options can be used in combination or on their own. 

### out Option

The `out` option defines an alternative folder to store the results to and takes the full path to the specified folder.

### Example Commands for out Option

- Run test list outputting the results in specified folder: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist" out="D:\SharedFolder"
````

![Run test list outputting the results in specified folder][7]

### result Option

The `result` sets specific name for the default result file and takes a file name in double quotes. 

### Example Commands for result Option

- Run test list outputting the results in specified folder and setting custom name for the result file: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist" out="D:\SharedFolder" 
result="customName"
````

![Run test list outputting the results in specified folder with custom name][8]

### xml or html Options

Use either the `xml`, or the `html` option to output the result into the corresponding file type - `*.xml` or `*.html` file. The different format result file is output in addition to the default result file with file extension `*.aiiresult`. 

> __Note__
><br>
> `xml` or `html` option is valid only when executing a test list. 

### Example Commands for xml or html Options

- Run test list outputting the results in xml format: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist" 
xml
```` 

![Run test list outputting the results in xml format][9]

- Run test list outputting the results in html format in specified folder and setting custom name for the result files: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist" out="D:\SharedFolder" 
result="customName" 
html
````

![Run test list outputting the results in html format in specified folder with custom name][10]

> __Note__
><br>
> Result files are saved into the project **Results** sub-folder if the `out` option is not used, and with default name if the `result` option is not used.

### junit or junitstep Options

Use the `junit` or `junitstep` options to output the result into a `junit(step).xml` result file. The difference between the two is whether to convert a test or a test step to a junit test in the output result.

### Example Commands for junit or junitstep Options

- Run test list outputting the results in junitstep format in specified folder and setting custom name for the result files: 

````cmd
>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
list="D:\Test Studio Projects\July2024\TestLists\demoList-ArtOfTest.aiilist" 
out="D:\SharedFolder" 
result="customName" 
junitstep
````

![Run test list outputting the results in junitstep format in specified folder with custom name][11]

- Run single test outputting the results in junit format: 

````cmd
>>"C:\Program Files (x86)\Progress\Test Studio\Bin\ArtOfTest.Runner.exe" 
test="D:\elle\Test Studio Projects\July2024\demoTest-AOTRunner.tstest" 
junit
````

![Run single test outputting the results in junit format][12]

> __Note__
><br>
> Result files are saved into the project **Results** sub-folder if the `out` option is not used, and with default name if the `result` option is not used.

### persistOnEachStep Option

By default the `PersistOnEachStep` option is _false_. If set to _true_ it saves the results after each executed step. It is used when debugging specific cases when the final result is not generated as expected.

## Option to Use Custom Settings for the Execution

By default the CLI runner execution uses the settings applied in the Settings.aiis file for a single test run, or the settings specified in the executed test list. The __ArtOfTest.Runner.exe__ supports customizing the execution by using custom settings file. 

### settings Option

The `settings` option takes the full path to a JSON file containing custom settings for the run. 

Below is an example of a complete JSON setting file that contains all of Telerik's test/test list run configuration settings. 

````JSON
{
  "Settings": {
      "__type": "ArtOfTest.WebAii.Core.Settings",
      "__value": {
        "ResponsiveWeb": {
          "__type": "ArtOfTest.WebAii.Core.Settings+ResponsiveWebSettings",
          "__value": {
            "Width": 0,
            "Height": 0,
            "UserAgent": null
          }
        },
        "Web": {
          "__type": "ArtOfTest.WebAii.Core.Settings+WebSettings",
          "__value": {
            "IsProfilingExecution": false,
            "ExecutingBrowsers": [],
            "UseMultiBrowserExecution": false,
            "RecycleBrowser": false,
            "AspNetDevServerPort": -1,
            "LocalWebServer": 0,
            "EnableUILessRequestViewing": false,
            "WebAppPhysicalPath": "",
            "DefaultBrowser": 10,
            "EnableScriptLogging": false,
            "BaseUrl": "",
            "KillBrowserProcessOnClose": false,
            "KillBrowsersBeforeStart": true,
            "AutoCalibrateBrowsers": false,
            "UseHttpProxy": false,
            "EnableSilverlight": false,
            "VerboseHttpProxy": false,
            "SilverlightConnectTimeout": 60000,
            "SilverlightApplicationPath": null,
            "WebComponents": true,
            "UseBrowserExtension": false,
            "ChromiumFirstInteractionDelay": 500,
            "FirefoxMinimumJSClickDelay": 100
          }
        },
        "Wpf": {
          "__type": "ArtOfTest.WebAii.Core.Settings+WpfSettings",
          "__value": {
            "DefaultApplicationPath": null,
            "DefaultApplicationArgs": null,
            "DefaultApplicationWorkingFolder": null
          }
        },
        "Desktop": {
          "__type": "ArtOfTest.WebAii.Core.Settings+DesktopSettings",
          "__value": {
            "DefaultApplicationPath": null,
            "DefaultApplicationArgs": null,
            "DefaultApplicationWorkingFolder": null
          }
        },
        "CreateLogFile": true,
        "LogLocation": "C:\\WebAiiLog\\",
        "QueryEventLogErrorsOnExit": false,
        "LogAnnotations": false,
        "SimulatedMouseMoveSpeed": 0.3,
        "ExecuteInDevelopmentTests": false,
        "WaitCheckInterval": 500,
        "ElementWaitTimeout": 15000,
        "SearchByImageFirst": false,
        "ExecuteCommandTimeout": 20000,
        "ExecutionDelay": 0,
        "RerunFailedTests": false,
        "UnexpectedDialogAction": 2,
        "AnnotateExecution": false,
        "AnnotationMode": 0,
        "RecordingMode": 0,
        "RecordingCodec": 0,
        "RecordingScale": 100,
        "RecordingFPS": 5,
        "RecordingOutputLocation": "",
        "RecordingSizeLimit": 0,
        "XMultiMgr": true,
        "ClientReadyTimeout": 60000,
        "DisableDialogMonitoring": false,
        "RunnerResponseTimeout": 0.0,
        "EnableImageSearch": true,
        "ElementImageSearchTimeout": 15000,
        "ElementImageSearchDelay": 300,
        "ScrollOnImageSearch": true,
        "TelerikComponentsVersion": 0
      }
    },
  "WebSettings": null,
  "PropertyBag": null
}
````

> __Tip__
><br>
> The settings listed in the settings file correspond to these available in the <a href="/getting-started/test-execution/test-list-settings" target="_blank">test list settings</a>.

<br>
<br>
<br>

## Publish Results To TFS

**Note:** All options listed in the help screen in relation to results publishing to TFS are mandatory. Below are some additional notes to each of the options. 

- The **server** option takes the TFS server name with its full path in double quotes like this **http://myTFS.myDomain.com:8080/tfs**.

- The **build** option takes the respective build which the results could be associated to.

- The **project** option takes the name of the current team project which the build belongs to.

- The **platform** option takes the respective platform which is usually Windows and thus the option takes value "win".

- The **flavor** defines if the build is Debug or Release (defaults to "Debug").

Below is a sample command to publish results to TFS from a test list execution.

![Publish Results to TFS][8]

## Exit Codes

__ArtOfTest.Runner.exe__ returns an exit code so the Build Server can check for it on process exit in case of an exception:

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
	<td><strong>0</strong></td><td>RUN_TESTS_SUCCESS </td><td>Run is processed and all tests passed.</td>
</tr>
<tr>
	<td><strong>1</strong></td><td>RUN_TESTS_ERROR</td><td>Run is processed and some tests failed.</td>
</tr>
<tr>
	<td><strong>2</strong></td><td>NOT_RUN_UNEXPECTED_ERROR</td><td>Run is not processed due to unexpected error.</td>
</tr>
<tr>
	<td><strong>3</strong></td><td>NOT_RUN_COMPILATION_ERROR</td><td>Run is not processed due to compilation errors.</td>
</tr>
<tr>
	<td><strong>10</strong></td><td>NOT_RUN_USAGE_INFO</td><td>No run to process, requested usage info.</td>
</tr>
<tr>
	<td><strong>11</strong></td><td>NOT_RUN_INVALID_COMMAND_ARGS</td><td>No run to process due to general invalid arguments error.</td>
</tr>
<tr>
	<td><strong>12</strong></td><td>NOT_RUN_TEST_NOT_FOUND</td><td>Run is not processed due to invalid test path argument.</td>
</tr>
<tr>
	<td><strong>13</strong></td><td>NOT_RUN_TESTLIST_NOT_FOUND</td><td>Run is not processed due to invalid test list path argument.</td>
</tr>
</table>


[1]: /img/features/test-runners/artoftest-runner/fig1.png
[2]: /img/features/test-runners/artoftest-runner/fig2.png

[4]: /img/features/test-runners/artoftest-runner/fig4.png
[5]: /img/features/test-runners/artoftest-runner/fig5.png
[6]: /img/features/test-runners/artoftest-runner/fig6.png
[7]: /img/features/test-runners/artoftest-runner/fig7.png
[8]: /img/features/test-runners/artoftest-runner/fig8.png
[9]: /img/features/test-runners/artoftest-runner/fig9.png
[10]: /img/features/test-runners/artoftest-runner/fig10.png
[11]: /img/features/test-runners/artoftest-runner/fig11.png
[12]: /img/features/test-runners/artoftest-runner/fig12.png