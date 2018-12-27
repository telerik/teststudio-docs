---
title: VSTest.Console.exe 
page_title: VSTest.Console.exe | Test Studio Dev Documentation
description: Test Studio Dev tests are recognized by VS Test Explorer and could be executed by it. 
position: 3
---
# VSTest.Console.exe#

The <a href="https://msdn.microsoft.com/en-us/library/jj155796.aspx" target="_blank">VSTest.Console.exe</a> in Visual Studio discovers and runs tests, including Test Studio Dev tests.

The VSTest Console is a CLI tool you can access from the developer command prompt.

There are two prerequsites two run test studio tests with the vstest.console:
* Your test project is already compiled in Visual Studio. 
* Newtonsoft.json is in the GAC. Check this article on <a href="https://docs.microsoft.com/en-us/dotnet/framework/app-domains/how-to-install-an-assembly-into-the-gac" target="_blank">how to add assemblies to the GAC using Gacutil</a>. 

To execute tests, simply call the vstest.console.exe with "yourtest.tstest" as argument.

>__Note!__ If you have unit tests you also need to specify the project .dll in the vstest.console arguments as shown in this example: vstest.console bin\debug\TestStudioProject.dll WebTest.tstest

![Start test][1]

Any results you output will appear in the vstest.console result deployment folder which by default resides in the project root. "{projectpath}\TestResults".

>__Note!__ For vstest.console.exe 15+ (distributed with VS2017) you need to add to also specify test adapter in the command arguments like this: vstest.console.exe baseurlnavigates.tstest   /TestAdapterPath:"C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow\Extensions". In addition the libraries listed below should be put in the GAC or in "C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\CommonExtensions\Microsoft\TestWindow\Extensions". Libraries to be included:
* __Autofac__
* __Newtownsoft.json__
* __Telerik.TestStudio.Shared__ 
You can find the libraries in the Test Studio install folder: C:\Program Files (x86)\Progress\Test Studio\Bin. Check the article above on some details on how to GAC assemblies in the Global Assembly Cache.

[1]: images/vs-test-console/fig1.png

