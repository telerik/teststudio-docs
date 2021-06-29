---
title: Execute Tests and Test lists with VSTestConsole.exe
page_title: Execute Test Studio Test and Test lists with VSTestConsole.exe
description: "Integrate Test Studio tests in TFS continuous integration builds. Execute Test Studio tests and test lists with VSTestConsole.exe"
position: 10
---
# Execute Test Studio Tests with VSTest.Console.exe #

The <a href="https://msdn.microsoft.com/en-us/library/jj155796.aspx" target="_blank">VSTest.Console.exe</a> in Visual Studio discovers and runs tests, including Test Studio tests and <a href="/automated-tests/vs-plugin/test-lists-in-vs-2017-2019" target="_blank">test lists</a>.

There are few requirements in order to execute Test Studio tests and test lists with the Visual Studio test runner VSTest.Console.exe. Follow the steps below to be able to trigger test runs with VSTest.Console.exe.

__1.__&nbsp; __Install Autofac.dll and Newtownsoft.Json.dll in the GAC__ (Global Assembly Cache). The dll files are stored in the Test Studio installation folder in the _bin_ subfolder - the default location is _C:\Program Files (x86)\Progress\Test Studio\Bin_.

> __Tip__
><br>
><br>
> Check the <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/how-to-install-an-assembly-into-the-gac" target="_blank">Microsoft documentation on how to install a dll file in the GAC (Global Assembly Cache)</a>.

__2.__&nbsp; __Start the VS Developer Command Prompt with Admin privilege__.

__3.__&nbsp; Change the __working folder__ to this, which __contains the vstest.console.exe__. Depending on the Visual Studio installation this can be:

* for **Visual Studio 2015** it is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* for **Visual Studio 2017 Enterprise** it is C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* for **Visual Studio 2019 Professional** it is C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow

__4.__&nbsp; __Set these two variables__ - ***TS_PROJECT_PATH*** (the folder, which contains the Test Studio project _Settings.aiis_) and ***TS_DLL_PATH*** (the folder, which contains the built project dll - by default it is in the project root under _\bin\Debug_).

```
set TS_PROJECT_PATH=C:\Projects\TestStudioProject11\TestStudioProject11

set TS_DLL_PATH=C:\Projects\TestStudioProject11\TestStudioProject11\bin\Debug\TestStudioProject11.dll
```

> __Important__
><br>
><br>
> These variables are __set for the current instance of the Developer Command Prompt__. By each next start of the command prompt the variables need to be set again.
><br>
><br>
> Therefore, if the tests are executed as part of CI setup, the two variables need to be set in the build tasks prior the task to run the test scripts.

__5.__&nbsp; The execution of Test Studio tests with VSTest.Console.exe requires the usage of the argument /TestAdapterPath:[path] - this is the __Telerik.TestStudio.TestAdapter-VS20XX.dll__ and can be found in the folder corresponding to the Visual Studio version in use:

* for **Visual Studio 2015** the TestAdapter.dll is in any of the sub-folders in the *Visual Studio Extensions* directory, which is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\Extensions\
* for **Visual Studio 2017 Enterprise** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2017
* for **Visual Studio 2019 Professional** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2019

__6.__&nbsp; __Visual Studio 2019 requires the argument /Settings:[_file name_]__, which accepts a Visual Studio <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">Test Explorer project settings file</a>.

## Examples

Below is listed sample commands to execute a Test Studio test and test list with the **VSTestConsole.exe in Visual Studio 2019**, after the **TS\_PROJECT\_PATH** and **TS\_DLL\_PATH** variables are set for the current instance of the VS Developer Command Prompt:

```
trigger Parent.tstest run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe "C:\Projects\TestStudioProject11\TestStudioProject11\Parent.tstest" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019" /Settings:"C:\Projects\TestStudioProject11\TestStudioProject11\TestSettings1.testsettings

trigger sampleList.aiilist run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe  "C:\Projects\TestStudioProject11\TestStudioProject11\TestLists\sampleList.aiilist" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019" /Settings:"C:\Projects\TestStudioProject11\TestStudioProject11\TestSettings1.testsettings
```
