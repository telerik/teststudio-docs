---
title: Troubleshooting Failure for Test Which Downloads File
description: This article provides troubleshooting steps for resolving a test failure that occurs on attempt to download file during test execution.
type: troubleshooting
page_title: Troubleshooting Test Failure when Downloading File | Test Studio | Telerik
slug: troubleshooting-test-failure-downloading-excel-file-test-studio
tags: troubleshooting, test failure, downloading, Excel file, Test Studio
res_type: kb
---

## Description

Executing a test in Test Studio that includes a step to download a file, the test fails with the following error:

````
Failure detected during execution. Details:
------------------------------------------------------------
System.ArgumentException: Open or Run downloaded file is not supported for ChromeHeadless.
   at ArtOfTest.WebAii.Design.IntrinsicTranslators.Descriptors.DownloadDialogHandlerDescriptor.CreateChromeHeadlessDialogs(Browser browser, List`1 dialogs)
   at ArtOfTest.WebAii.Design.IntrinsicTranslators.Descriptors.DownloadDialogHandlerDescriptor.InitializeDialogs(Browser browser)
   at ArtOfTest.WebAii.Design.Execution.ExecutionContext.SetDialogMonitoring(AutomationStepList steps, TestType testType)
   at ArtOfTest.WebAii.Design.Execution.ExecutionContext.SetDialogMonitoring(Test test)
   at ArtOfTest.WebAii.Design.Execution.ExecutionContext.SetDialogMonitoring()
   at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InternalExecuteTestIteration(Object codeBehindInstance, Boolean isDataDriven)
   at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.InternalExecuteTest(Test test, TestResult initializationResult)
   at ArtOfTest.WebAii.Design.Execution.TestExecuteProxy.ExecuteTest(ExecuteTestCommand command)
````

The error occurs when running the test with the regular Chrome browser, not just the headless version. Running the test in Edge and Firefox behaves the same way and fails with the same error. 

## Solution

The error is related to the type of `HandleButton` selected in the Handle Download Dialog step. Follow the steps below to fix it: 

1. Open the test project in Test Studio.
2. Locate the step that downloads file.
3. In the properties of the step, ensure that the <a href="/features/dialogs-and-popups/dialogs#handle-button" target="_blank">`HandleButton` property</a> of the Download step is set to "Save".
4. Save the applied changes.
5. Run the test again.


By setting the `HandleButton` property to "Save", Test Studio will handle the download dialog and save the file instead of attempting to directly open or run it.




