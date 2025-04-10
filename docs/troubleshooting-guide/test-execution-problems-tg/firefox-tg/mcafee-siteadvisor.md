---
title: McAfee SiteAdvisor blocks execution 
page_title: McAfee SiteAdvisor blocks execution
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# McAfee SiteAdvisor blocks execution

## PROBLEM

I cannot execute a test in Firefox. I receive the following error in the test log:

*Outer Exception Type: System.TimeoutException
     Message: Wait for condition has timed out
     HRESULT: 0x80131505 (Official ID (if app.) = COR_E_TIMEOUT, Error Bit = FAILED, Facility = FACILITY_URT, Code = 5381)
     Call Stack:
          at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo, Object target)
          at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout, WaitResultType errorResultType)
          at ArtOfTest.Common.WaitSync.For[T](Predicate`1 predicate, T target, Boolean invertCondition, Int32 timeout)
          at ArtOfTest.WebAii.Core.Manager.WaitForBrowserToConnect(Int32 browserIndexToWaitFor)
          at ArtOfTest.WebAii.Core.Manager.LaunchNewBrowser(BrowserType browserToLaunch, Boolean waitForBrowserToConnect, ProcessWindowStyle windowStyle, String arguments)
          at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InitializeWeb(ExecutionEngineCreateParams initParams)
          at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.CreateAndInitializeEngine(Test test, ExecutionEngineCreateParams cp)
          at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)*

## SOLUTION

In some cases **McAfee SiteAdvisor** could block the test execution in **FireFox**. Disable it or uninstall it in order to prove whether the antivirus software causes the execution problems.

