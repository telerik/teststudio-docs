---
title: Running Multiple WPF Tests in Telerik Test Studio Without Relaunching the Application
description: Learn how to configure multiple WPF tests in Telerik Test Studio to run on the same application instance without relaunching it.
type: how-to
page_title: How to Execute Multiple WPF Tests on a Single Application Instance in Telerik Test Studio
slug: run-multiple-wpf-tests-single-instance
tags: progress, telerik, teststudio, wpf, test, application, launch
res_type: kb
ticketid: 1650109
---

## Description

When conducting multiple WPF tests in Telerik Test Studio, the default behavior launches the application for each test, which may not be desirable if the intention is to run all tests on the same application instance. This KB article provides workarounds to configure tests or test lists to avoid relaunching the application for each test execution.

This KB article also answers the following questions:
- How can I run multiple WPF tests on the same application instance in Telerik Test Studio?
- What are the steps to configure a test list to not relaunch the application for each test in Telerik Test Studio?
- How do I attach a test to a running WPF application in Telerik Test Studio?

## Solution
To prevent relaunching the application for each WPF test execution, use one of the following workarounds:

### Use One Parent Test
- Create a parent test and insert multiple tests as steps using the [Test as Step](https://docs.telerik.com/teststudio/features/custom-steps/all-tests-common/test-as-step) feature. This method allows you to replicate a test list where execution remains within the main test's context.

### Adjust Test Configuration
- Configure your tests to either attach to a running instance of the application or launch it if not running. Follow these steps:
  1. Use a dummy WPF application for test configuration that launches as expected. This is only for setting up the test and not used in actual recording or execution. See [WPF Test Configuration](https://docs.telerik.com/teststudio/automated-tests/wpf/wpf-test) for guidance.
  2. Add a coded step at the beginning of each test. Insert an empty coded step as described [here](https://docs.telerik.com/teststudio/automated-tests/coded-tests/coded-step#insert-empty-coded-step).
  3. Use the code sample from [Connecting to a Running App](https://docs.telerik.com/teststudio/advanced-topics/coded-samples/wpf/connect-to-running-app) and modify it according to your application's process name.
  4. You can initiate a recording session by attaching the recorder to the already running application following [this guide](https://docs.telerik.com/teststudio/automated-tests/recording/overview#attach-the-recorder-to-a-running-application), or use the Run->To Here option for partial test run to execute the first coded step and launch the application.
  5. Ensure to include closing the application in the automated scenario, which can be done through an Execution extension. Use the `OnAfterTestListCompleted()` method as detailed [here](https://docs.telerik.com/teststudio/advanced-topics/coded-samples/general/execution-extensions).

### Additional Notes
- Consider voting for the [feature request](https://feedback.telerik.com/teststudio/1530999-reuse-wpf-application-in-test-list-execution) to reuse the WPF application instance during test list execution to increase its priority.

## See Also
- [Test as Step](https://docs.telerik.com/teststudio/features/custom-steps/all-tests-common/test-as-step)
- [WPF Test Configuration](https://docs.telerik.com/teststudio/automated-tests/wpf/wpf-test)
- [Insert Empty Coded Step](https://docs.telerik.com/teststudio/automated-tests/coded-tests/coded-step#insert-empty-coded-step)
- [Connecting to a Running App](https://docs.telerik.com/teststudio/advanced-topics/coded-samples/wpf/connect-to-running-app)
- [Execution Extensions](https://docs.telerik.com/teststudio/advanced-topics/coded-samples/general/execution-extensions)
