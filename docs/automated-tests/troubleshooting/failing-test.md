---
title: How to Troubleshoot a Failing Test
page_title: How to Troubleshoot My Failing Test?
description: "Learn how to debug or troubleshoot a failing test in Test Studio. If you experience issues like Element not found exception, your test fails to locate an element on a page, or the test fails on a random step on each run, this article will help you." 
position: 0
---
# Troubleshoot My Failing Test

Test Studio has built-in mechanisms to help you identify the weak spots in your tests. If a particular step fails, you can find enough details about the cause.

The <a href="/automated-tests/test-execution/quick-execution" target="_blank">Quick Test Execution mode</a> in Test Studio gives different options for troubleshooting a failing test. This article will guide you through the available tools and how to get the most of them.

- __[Execution Log](#execution-log-on-failure)__
- __[Step Failure Details](#step-failure-details)__
- __[Visual Debugger](#visual-debugger)__
- __[Application Log](#test-studio-application-log)__

## Execution Log on Failure

The <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">execution log</a> generated in the quick run mode is available only temporarily, but it still contains an abundance of details like:

- A list with the steps in the executed test, including tests as step.
- A note about which steps were run.
- A note about which steps passed or failed.
- Details about the error and information the cause.
- Information about the browser used for the test.
- The current Test Studio version.
- The executed test.

![execution Log](/img/automated-tests/troubleshooting/failing-test/fig1.png)

### What to Look for in the Execution Log on Failure?

When a test fails, check the **Failure Information** under the failed step. These details will help you find the root cause of the failure. In the example below, the element in step 5. <a href="/automated-tests/troubleshooting/element-not-found" target="_blank">cannot be found on the page</a>. If you use image search, you will also see the element's find expression. Finally, you'll find a link to a relevant documentation article.

![failure in execution log](/img/automated-tests/troubleshooting/failing-test/fig2.png)

> __Tip__
><br>
><br>
> Before you try to change the find expression for the missing element, inspect the images on failure in the <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">Step Failure Details dialog</a> and ensure that the test has reached the page where you expect to find the missing element.

## Step Failure Details

The <a href="/automated-tests/test-results/step-failure-details" target="_blank">Step Failure Details dialog</a> is available only when a test fails. It provides a full information stack to help you analyze and resolve a failing step.

### Failure Tab

The <a href="/automated-tests/test-results/step-failure-details#failure-tab" target="_blank">__Failure__ tab</a> shows the error that caused the failure and provides access to the full execution log.

![failure tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig3.png)

> __Tip__
><br>
><br>
> With the **Export** button, you can <a href="/automated-tests/test-results/step-failure-details#how-to-export-the-step-failure-details" target="_blank"> download the complete failure log</a> and provide it to a colleague or the Test Studio Support team.

### Images Tab

The <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">__Images__ tab</a> compares the visual representation of the tested page at the time of failure with the expected state. The actual page could have changed due to an application update or because the previous steps in the test did not manage to navigate to the desired page state.

![images tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig4.png)

> __Tip__
><br>
><br>
> If the actual page is not the same as the expected and there have been no recent changes in the application, you may need to delay the test steps execution so that they can be executed when the page is ready to respond. To adjust the step execution speed with the application responsiveness, you can use <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">wait</a> and <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">verification steps</a>, and <a href="/features/custom-steps/execution-delay" target="_blank">execution delays</a>.

### Page DOM Tab

The <a href="/automated-tests/test-results/step-failure-details#page-dom-tab" target="_blank">__Page DOM__ tab</a> provides a snippet of how Test Studio sees the DOM of the page at the time of failure. You can inspect the overall structure of the page in the DOM or search for a particular element. This tab is helpful when the failure is related to the state of an element, for example:

- The element cannot be found.
- The element does not exist.
- The test times out while waiting for an element.
- The test targets an incorrect element.

![DOM Tree tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig5.png)

> __Tip__
><br>
><br>
> If you need to explore the DOM tree in real time, you can use the <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">Visual Debugger</a>. If you need to explore the DOM tree in a recording session, you can use the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer in the Advanced Recording Tools window</a>.

### Resolve Failure

The  <a href="/automated-tests/test-results/step-failure-details#resolve-failure-tab" target="_blank">__Resolve Failure__ tab</a> in the **Step Failure Details** dialog provides a suggestion based on the actual error. Therefore, it will present different information for the various failures you may encounter.

![Resolve Failure tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig6.png)

## Visual Debugger

The <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">Visual Debugger</a> allows you to debug a test during quick test execution. It appears in the bottom right corner of the active display (right above the Windows system tray) and shows the progress of the executed steps. From the Visual Debugger toolbar, you can <a href="/automated-tests/troubleshooting/visual-debugger#manually-pause-the-test" target="_blank">manually pause</a> the test run or adjust its settings to <a href="/automated-tests/troubleshooting/visual-debugger#set-auto-pause-rule-for-the-visual-debugger" target="_blank">automatically pause on specific errors</a>. You can also set a breakpoint on a particular step and force the test execution to pause on that step.

![Visual Debugger](/img/automated-tests/troubleshooting/failing-test/fig7.png)

Once the test is <a href="/automated-tests/troubleshooting/visual-debugger#make-use-of-the-visual-debugger-tool-options-during-test-run" target="_blank">paused during run-time</a>, you can:

- Inspect the current DOM of the page.
- Take a snippet of the DOM and a screenshot of the page.
- Access the execution log of the steps executed so far.
- Diagnose the current failed step, if applicable.
- Report a bug if there is a bug tracker configured for the project.

Once you explore the failure details, you can <a href="/automated-tests/troubleshooting/visual-debugger#resume-the-test-execution" target="_blank">resume the test execution</a> until the end of the test or one step at a time. You can also choose to rerun the current step.

![Visual Debugger in Paused mode](/img/automated-tests/troubleshooting/failing-test/fig8.png)

## Test Studio Application Log

The application log contains messages recorded by Test Studio during your interaction with the product. All records in the application log are designed to indicate important events and help you pinpoint where problems may occur. This log is distinct from the execution log, which only records the attempted steps and encountered exceptions during test execution. The application log is useful for unexpected occurrences such as a product crash, unexpected termination of a test run, which prevents generating the execution log, inconsistent behavior while working with the project components.

To easily find the useful records in the application log, it is recommended to first clear the logging, ensure it is enabled, and reproduce the error that must be investigated. Once the error is reproduced, open the application log in a text editor (usually Notepad). If you need to send the log, you can save the file and provide it zipped.

![Test Studio Application Log](/img/automated-tests/troubleshooting/failing-test/fig9.png)

**When to turn on the application log?**

Whenever Test Studio behaves differently than expected, an application log can give more information about the reason. This is especially true for situations other than test failure or code compilation. For example:

- Test Studio generates error messages.
- Test Studio closes unexpectedly.
- Test Studio stops responding.
- Test Studio interacts with other software (TeamPulse, TFS, QC) differently than expected.
- A Test Studio execution browser closes unexpectedly or stops responding during execution.
- Test Studio cannot connect to a browser.

**Generating the application log.**

You can <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">generate an application log</a> from the help tab.

**What to look for in the application log.**

The application log can be useful in many ways to Test Studio support engineers and developers. If you encounter issues, look for any exceptions.

![Log][1]

These are usually accompanied by error messages that may guide you in troubleshooting. If you are not familiar with the error message, try searching our documentation for it. If you still cannot understand the error, consider attaching a copy of the log to a <a href="/knowledge-base/best-practices-kb/submit-support-ticket" target="_blank">support ticket</a>. 

[1]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log/fig1.png