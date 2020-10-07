---
title: Execute Tests and Test lists with VSTestConsole.exe
page_title: Execute Test Studio Test and Test lists with VSTestConsole.exe
description: "Integrate Test Studio tests in TFS continuous integration builds. Execute Test Studio tests and test lists with VSTestConsole.exe"
position: 10
---
# Execute Test Studio Tests with VSTestConsole.exe #

To be able to execute <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests with the Visual Studio default test runner there are few requirements to set in advance. These are described below:

1.&nbsp; Start the **VS Developer Command Prompt** with Admin privilege.

2.&nbsp; Change the working folder to be the one which contains the vstest.console.exe. This depends on the Visual Studio installation:

* for **Visual Studio 2015** it is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* for **Visual Studio 2017 Enterprise** it is C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* for **Visual Studio 2019 Professional** it is C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow

3.&nbsp; There are two variables you have to set before executing Test Studio tests - ***TS_PROJECT_PATH*** and ***TS_DLL_PATH***. Project path is the folder which contains the Settings.aiis file. Dll path is the folder which contains the built project dll. 

```
set TS_PROJECT_PATH=C:\Projects\TestStudioProject11\TestStudioProject11

set TS_DLL_PATH=C:\Projects\TestStudioProject11\TestStudioProject11\bin\Debug\TestStudioProject11.dll
```

> __Note!__ The variables are set for this instance of the Developer Command Prompt. By each next start of the command prompt the variables need to be set again. Therefore these need to be set in the build tasks in __CI environment__ prior the task to execute the test.

4.&nbsp; To be able to execute a Test Studio test, you need to include the /TestAdapterPath:[path] argument, except the full path to the *.tstest file - this is the __Telerik.TestStudio.TestAdapter-VS2015.dll__. The location of this dll depends on the Visual Studio installation:

* for **Visual Studio 2015** the TestAdapter.dll is in any of the sub-folders in the *Visual Studio Extensions* directory, which is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\Extensions\
* for **Visual Studio 2017 Enterprise** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2017
* for **Visual Studio 2019 Professional** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2019

Below is listed a sample command to execute a Test Studio test with the **VSTestConsole.exe in Visual Studio 2019**, after the **TS\_PROJECT\_PATH** and **TS\_DLL\_PATH** variables are set for the current instance of the *VS Developer Command Prompt*:

```
trigger Parent.tstest run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe "C:\Projects\TestStudioProject11\TestStudioProject11\Parent.tstest" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019"

trigger sampleList.aiilist run

C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console.exe  "C:\Projects\TestStudioProject11\TestStudioProject11\TestLists\sampleList.aiilist" /TestAdapterPath:"C:\Program Files (x86)\Progress\Test Studio\VS2019"
```

>__Note!__ In addition to all of the above, for vstest.console.exe 15+ (distributed with VS2017 and later) the libraries listed below should be <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/how-to-install-an-assembly-into-the-gac" target="_blank">installed in the GAC</a> or copied and referred in the project from the folder, where the TestAdapter dll is - _C:\Program Files (x86)\Progress\Test Studio\VS2017_ for VS 2017 and _C:\Program Files (x86)\Progress\Test Studio\VS2019_ for VS 2019. Libraries to be included:
<br>
* __Autofac__
* __Newtownsoft.json__
* __Telerik.TestStudio.Shared__ 
* __Telerik.TestStudio.SourceControl__ 
<br>
<br>
You can find the libraries in the Test Studio install folder: _C:\Program Files (x86)\Progress\Test Studio\Bin_.
