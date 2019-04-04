---
title: VSTest.Console.exe 
page_title: VSTest.Console.exe | Test Studio Dev Documentation
description: Test Studio Dev tests are recognized by VS Test Explorer and could be executed by it. 
position: 3
---
# VSTest.Console.exe

The <a href="https://msdn.microsoft.com/en-us/library/jj155796.aspx" target="_blank">VSTest.Console.exe</a> in Visual Studio discovers and runs tests, including Test Studio Dev tests.

The VSTest Console is a CLI tool you can access from the developer command prompt.

There are two prerequisites to run test studio tests with the vstest.console.exe:

* Your test project is already compiled in Visual Studio.
* Newtonsoft.json is in the GAC. Check this article on <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/how-to-install-an-assembly-into-the-gac" target="_blank">how to add assemblies to the GAC using Gacutil</a>.

## Visual Studio 2015

To execute tests, simply call the vstest.console.exe with "yourtest.tstest" as argument.

>__Note!__ If you have unit tests you also need to specify the project .dll in the vstest.console arguments as shown in this example: vstest.console bin\debug\TestStudioProject.dll WebTest.tstest

![Start test][1]

Any results you output will appear in the vstest.console result deployment folder which by default resides in the project root. "{projectpath}\TestResults".

## Visual Studio 2017 and Later

1.&nbsp; Start the **VS Developer Command Prompt** with Admin privilege.

2.&nbsp; Change the working folder to be the one which contains the vstest.console.exe. This depends on the Visual Studio installation:

* for **Visual Studio 2017 Enterprise** it is C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TestWindow
* for **Visual Studio 2019 Professional** it is C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow

3.&nbsp; There are two variables you have to set before executing Test Studio tests - ***TS_PROJECT_PATH*** and ***TS_DLL_PATH***. Project path is the folder which contains the Settings.aiis file. Dll path is the folder which contains the built project dll. 

```
set TS_PROJECT_PATH=C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11

set TS_DLL_PATH=C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11\bin\Debug\TestStudioProject11.dll
```

> __Note!__ The variables are set for this instance of the Developer Command Prompt. By each next start of the command prompt the variables need to be set again. Therefore these need to be set in the build tasks in __CI environment__ prior the task to execute the test.

4.&nbsp; To be able to execute a Test Studio test, you need to include the /TestAdapterPath:[path] argument, except the full path to the *.tstest file - this is the __Telerik.TestStudio.TestAdapter-VS2015.dll__. The location of this dll depends on the Visual Studio installation:

* for **Visual Studio 2017 Enterprise** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2017
* for **Visual Studio 2019 Professional** the TestAdapter.dll is deployed in a sub folder of the Test Studio installation folder C:\Program Files (x86)\Progress\Test Studio\VS2019

Below is listed a sample command to execute a Test Studio test with the **VSTestConsole.exe in Visual Studio 2015**, after the **TS\_PROJECT\_PATH** and **TS\_DLL\_PATH** variables are set for the current instance of the *VS Developer Command Prompt*:

```
C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow>vstest.console "C:\Visual Studio 2015\Projects\TestStudioProject11\TestStudioProject11\Parent.tstest" /TestAdapterPath:"C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\Extensions\t1fos0ab.vkx"
```

>__Note!__ In addition for vstest.console.exe 15+ (distributed with VS2017 and later) the libraries listed below should be put in the GAC or in "C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow\Extensions". Libraries to be included:
<br>
* __Autofac__
* __Newtownsoft.json__
* __Telerik.TestStudio.Shared__ 
<br>
<br>
You can find the libraries in the Test Studio install folder: C:\Program Files (x86)\Progress\Test Studio\Bin. Check the article above on some details on how to GAC assemblies in the Global Assembly Cache.

[1]: images/vs-test-console/fig1.png
