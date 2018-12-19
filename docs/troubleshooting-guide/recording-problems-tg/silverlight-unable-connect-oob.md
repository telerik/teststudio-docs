---
title: Unable to connect to Silverlight OOB 
page_title: Unable to Connect to Silverlight OOB 
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Unable to Connect to Silverlight Out Of Browser Application 

## PROBLEM

I am not able to record my Silverlight out of browser application. It fails to attach with the following errors:


Outer Exception Type: System.TimeoutException<br/>
Message: Wait for condition has timed out<br/>
HRESULT: 0x80131505 (Official ID (if app.) = COR_E_TIMEOUT, Error Bit = FAILED, Facility = FACILITY_URT, Code = 5381)<br/>
Call Stack:<br/>
at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo, Object target)<br/>
at ArtOfTest.Common.WaitSync.For\[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)
at ArtOfTest.Common.WaitSync.For\[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)

at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)

at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect, ProcessWindowStyle windowStyle, String arguments)

at Telerik.TestStudio.Web.IERecorder.IERecorderManager.LaunchNewRecorder(Action`2 asyncCallback, FloatingUIMode mode, BrowserType browserType, String arguments)

##Solution

This behavior appears on systems which have the <a href="https://technet.microsoft.com/en-us/library/security/MS15-049">MS15-049</a> security fix (KB3058985) installed. It is included in Silverlight version 5.1.40416 and later.

This security fix was addressed in Windows Updates on 12th of May, 2015. The patch prevents an elevation of privilege issue by restricting Silverlight applications running inside sllauncher.exe (the out-of-browser Silverlight container) to a **low integrity level**. 



You may wish to uninstall KB3058985 security patch or downgrade Silverlight bellow version 5.1.40416 to allow recording the Silverlight OOB applications.

