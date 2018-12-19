---
title: Extension Not Installed
page_title: Firefox Extension Not Installed
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Firefox Extension Not Installed

## PROBLEM

I cannot execute a test in Firefox. I receive the following error in the test log:

*System.TimeoutException: Wait for condition has timed out<br>
   at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo)<br>
   at ArtOfTest.Common.WaitSync.For\[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)<br>
   at ArtOfTest.Common.WaitSync.For\[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)<br>
   at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)<br>
   at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect, ProcessWindowStyle windowStyle, String arguments)<br>
   at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InitializeWeb(ExecutionEngineCreateParams initParams)<br>
   at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.CreateAndInitializeEngine(Test test, ExecutionEngineCreateParams cp)<br>
   at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)*

And the following displays in the Firefox URL field:

*about:blank?!!AOT2.0!Pipe.ArtOfTest.WebAii.BrowserProvisioner_##########*

## SOLUTION

**Test Studio 2017 R3 (v. 2017.3.1010) And Later**

There is a single extension combining the recording and execution which could be downloaded from the Mozzila Extension Page. For your convenience here is a direct link to the <a href="https://addons.mozilla.org/en-US/firefox/addon/progress-test-studio-extension/" target="_blank">**Progress Test Studio Extension**</a>.

>If you face any troubles when installing or enabling the extension please expand the **Extension Install Procedure** section <a href="/getting-started/configure-your-browser/firefox#Extension_Install" target="_blank">in this article</a>.

**Test Studio 2017 R2 SP1(v. 2017.2.824) And Earlier**

1.&nbsp; Check the Progress Testing Framework extension in Add-ons Manager. Click **Tools > Add-ons** (or Ctrl+Shift+A). Ensure __Progress Test Studio Firefox Execution__ is enabled. If they are not enabled please check <a href="/troubleshooting-guide/browser-inconsistencies-tg/extensions-disabled-in-ff" target="_blank">this article</a>.

![Add-ons][1]

2.&nbsp; If that is correct and it still doesn't work, there may be a conflicting Add-on. Try disabling all non-Telerik Add-ons and try again. If it succeeds, re-enable those Add-ons one at a time until you identify the culprit.

> Restart Firefox after making changes in the Add-ons Manager.

3.&nbsp; If the issue persist, try to reinstall Firefox first and then Test Studio.

4.&nbsp; As a last resort you can perform manual installation of the extensions by following these steps:

- Verify that in the *C:\Program Files (x86)\Telerik\Test Studio\Browser Extensions\Firefox4+* folder you can see the following files:

![FF4][2]

- Open the Windows registry.

- Navigate to the following path in the registry:

 - For 64bit version: **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Mozilla\Firefox\Extensions\**

 - For 32bit version: **HKEY_LOCAL_MACHINE\SOFTWARE\Mozilla\Firefox\Extensions\**

- You need to have the registry shown in the following screenshot:

![Edit String][3]

- If it doesn't look like the one in the screenshot, you need to create a new 'String Value' with:

Key: ** webaii21_FF4@telerik.com**  
Value: **C:\Program Files\Telerik\Test Studio\Browser Extensions\Firefox4+\**

-  Once this is done, open Firefox and go to your Firefox Extensions. Now you should be able to see the "Telerik Testing Framework - Firefox Http Client" extension. Simply enable it and you should be good to go.

> If you're using Symantec Antivirus Protection, its <a href="http://www.symantec.com/business/support/index?page=content&id=TECH95347" target="_blank">Intrusion Prevention System</a> may be interfering with the Test Studio Firefox extension.
> 
- Disable Symantec Intrusion Prevention.
- Load Firefox and enable the Telerik Testing Framework extension in Add-ons Manager.


[1]: /img/troubleshooting-guide/browser-inconsistencies-tg/extensions-disabled-in-ff/fig1.jpg
[2]: /img/troubleshooting-guide/test-execution-problems-tg/firefox-tg/extension-not-installed/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/firefox-tg/extension-not-installed/fig3.png