---
title: Execute Test Studio Tests with VSTestConsole.exe
page_title: Execute Test Studio Test with VSTestConsole.exe - Test Studio Dev Documentation
description: Execute Test Studio Test with VSTestConsole.exe 
position: 10
---
# Execute Test Studio Tests with VSTestConsole.exe #

To be able to execute Test Studio tests with the Visual Studio default test runner there are few requirements to set in advance. These are described below:

1.Start the VS Developer Command Prompt with Admin privilege.

2.Change the working folder to be the one which contains the vstest.console.exe. This is depending on the Visual Studio installation - for Visual Studio 2015 this is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow

3.There are two variables you have to set before executing Test Studio tests - ***TS_PROJECT_PATH*** and ***TS_DLL_PATH***. Project path is the folder which contains the Settings.aiis file. Dll path is the folder which contains the built project dll. 

```
set TS_PROJECT_PATH=C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11

set TS_DLL_PATH=C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11\bin\Debug\TestStudioProject11.dll
```

> __Note!__ The variables are set for this instance of the Developer Command Prompt. By each next start of the command prompt the variables need to be set again. Therefore these need to be set in the build tasks in __CI environment__ prior the task to execute the test.

4.To execute a Test Studio test except the full path to the *.tstest file you need to include the /TestAdapterPath:[path] argument - this is the __Telerik.TestStudio.TestAdapter-VS2015.dll__. 

The TestAdapter dll will be in any of the sub-folders in the Visual Studio Extensions directory which is C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\Extensions\ for default Visual Studio 2015 installation. Find the exact folder which contains the TestAdapter.dll and pass it as the /TestAdapterPath:[path] argument.

Below you may find a sample command to execute a Test Studio test with the VSTestConsole.exe after the TS\_PROJECT\_PATH and TS\_DLL\_PATH variables are set for the current instance of the VS Developer Command Prompt:

```
C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console "C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11\Parent.tstest" /TestAdapterPath:"C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\Extensions\t1fos0ab.vkx"
```
