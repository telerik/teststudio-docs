---
title: Internet Explorer could not record/execute a test
page_title: Internet Explorer could not record/execute a test
description: "Internet Explorer could not record/execute a test in Test Studio. Is there a specific setting to adjust in order to use IE for recording and executing Test Studio test"
position: 1
---
# Internet Explorer 11 could not record/execute a test

## PROBLEM

Internet Explorer 11 is successfully calibrated by Test Studio and <a href="/getting-started/installation/configure-windows-server" target="_blank">IE Enhanced Security (Windows Server OS)</a> is turned off. Though when trying to execute a test in Internet Explorer once the browser is launched it stops on the "about:blank page" and the test times out. In the execution log the following exception is recorded:

	System.TimeoutException: Wait for condition has timed out
   	at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo, Object target)
   	at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)
   	at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)
   	at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)
   	at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect, ProcessWindowStyle windowStyle, String arguments)
   	at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InitializeWeb(ExecutionEngineCreateParams initParams)
   	at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.CreateAndInitializeEngine(Test test, ExecutionEngineCreateParams cp)
   	at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)
 

## SOLUTION

Download and install <a href="https://www.microsoft.com/en-us/download/details.aspx?id=30656" target="_blank">Team Explorer</a>.  


