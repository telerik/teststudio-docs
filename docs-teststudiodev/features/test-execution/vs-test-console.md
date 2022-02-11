---
title: Execute Test Studio Dev Tests with VSTest.Console.exe 
page_title: Execute Test Studio Dev Tests with VSTest.Console.exe | Test Studio Dev Documentation
description: "Execute Test Studio Dev tests and test lists via command line with the Visual Studio vstest.console.exe"
position: 3
---
# Execute Test Studio Dev Tests with VSTest.Console.exe

The <a href="https://msdn.microsoft.com/en-us/library/jj155796.aspx" target="_blank">VSTest.Console.exe</a> is the Visual Studio command-line command that is used to run tests, including Test Studio Dev recorded tests and <a href="/features/test-execution/test-lists-in-vs-2017-2019" target="_blank">test lists</a>.There are few prerequisites to setup in order to enable a machine to execute Test Studio Dev tests and test lists via the VSTest.Console.exe. 

This article describes all necessary settings, as well as example commands.

- [Add Test Studio Dev dlls to the GAC](#install-test-studio-dev-specific-dlls-in-gac)
- [Set Test Studio Dev specific variables for the VS Command Prompt](#configure-the-vs-developer-command-prompt)
- [Tailor up the command for the VSTest.Console.exe](#list-the-vstestconsoleexe-command)
- [Examples](#example-commands)

## Install Test Studio Dev Specific DLLs in GAC

Install __Autofac.dll__ and __Newtownsoft.Json.dll__ in the <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/gac" target="_blank">GAC (Global Assembly Cache)</a>. The mentioned dll files are distributed in the Test Studio Dev installation folder under the _bin_ subfolder. The default install location is _C:\Program Files (x86)\Progress\Test Studio\_.

> __Tip__
><br>
><br>
> Read <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/how-to-install-an-assembly-into-the-gac" target="_blank">how to install a dll file in the GAC</a> if you need help on the topic.

## Configure the VS Developer Command Prompt

__1.__&nbsp; Start the VS Developer Command Prompt with __Admin rights__.

__2.__&nbsp; Change the __working folder__ to the one, which __contains the vstest.console.exe__. Choose it depending on the Visual Studio installation you have:

* **Visual Studio 2015 Professional** it is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* **Visual Studio 2017 Enterprise** it is C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* **Visual Studio 2019 Professional** it is C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* **Visual Studio 2022 Professional** it is C:\Program Files\Microsoft Visual Studio\2022\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow

__3.__&nbsp; __Set the following two variables__ - ***TS_PROJECT_PATH*** (the folder, which contains the Test Studio project _Settings.aiis_) and ***TS_DLL_PATH*** (the folder, which contains the built project dll - by default it is in the project root under _\bin\Debug_).

```
set TS_PROJECT_PATH=C:\Projects\TestStudioProject11\TestStudioProject11

set TS_DLL_PATH=C:\Projects\TestStudioProject11\TestStudioProject11\bin\Debug\TestStudioProject11.dll
```

> __Important!__
><br>
><br>
> These variables are __set for the current instance of the Developer Command Prompt__. By each next start of the command prompt the variables need to be set again.
><br>
><br>
> Thus, if executing the tests as part of CI setup, include tasks in the build to set these two variables prior the task to run the test scripts.

## List the VSTest.Console.exe Command

__1.__&nbsp; To trigger execution of Test Studio Dev tests from the VSTest.Console.exe you need to force its process to __use custom test adapters__ from a specified path in the test run. This is listed with the argument __/TestAdapterPath:[path]__ and the __Telerik.TestStudio.TestAdapter-VS20XX.dll__ to choose depends on the Visual Studio version in use:

* **Visual Studio 2015** - the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\TestAdapterVS2015
* **Visual Studio 2017** - the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2017
* **Visual Studio 2019** - the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2019
* **Visual Studio 2022** - the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder
C:\Program Files (x86)\Progress\Test Studio\VS2022

__2.__&nbsp; It is recommended to use the argument __/Settings:[fullPathToFile]__ (it is __mandatory for VS 2019__), which allows you to pass different run settings for the test execution. This argument accepts the *.testsettings file used to control <a href="/advanced-topics/project-configuration/test-explorer-settings" target="_blank">the execution from the Test Explorer</a>

## Example Commands

Below are listed sample commands to execute a Test Studio test and test list with the **VSTestConsole.exe in Visual Studio 2019**, after the **TS\_PROJECT\_PATH** and **TS\_DLL\_PATH** variables are set for the current instance of the VS Developer Command Prompt:

```
trigger Parent.tstest run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe "C:\Projects\TestStudioProject11\TestStudioProject11\Parent.tstest" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019" /Settings:"C:\Projects\TestStudioProject11\TestStudioProject11\TestSettings1.testsettings

trigger sampleList.aiilist run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe  "C:\Projects\TestStudioProject11\TestStudioProject11\TestLists\sampleList.aiilist" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019" /Settings:"C:\Projects\TestStudioProject11\TestStudioProject11\TestSettings1.testsettings
```
