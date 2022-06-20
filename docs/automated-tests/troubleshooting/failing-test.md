---
title: How to Troubleshoot a Failing Test
page_title: How to Troubleshoot My Failing Test?
description: "Test Studio - debug a failing test. How to understand what causes the test to fail. What options I have to debug or troubleshoot a failing test. My test fails with Element not found exception. My test fails to locate an element on page. My test fails on random step on each run." 
position: 0
---
# Troubleshoot My Failing Test

Test Studio has built-in mechanisms to help you identify the weak spots in your tests. In the case of a step failure you can find thorough details about what caused it.

The <a href="/automated-tests/test-execution/quick-execution" target="_blank">Quick Test Execution mode</a> in Test Studio gives different options for troubleshooting a failing test. This article will guide you through the available tools, when these are helpful or applicable and how to get the most of each.

- __[Execution Log](#execution-log-on-failure)__
- __[Step Failure Details](#step-failure-details)__
- __[Visual Debugger](#visual-debugger)__
- __[Application Log](#test-studio-application-log)__

## Execution Log on Failure

Although the <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">execution log</a> generated in the quick run mode, is a temporary available resource, it contains a bunch of useful details to help you analyze why a test may be failing.

It represents a list of the steps in the executed test including test as steps, noting which of these were run, and if they passed or failed. And in case of failure, there is detailed information for the error, which led to it.

![execution Log](/img/automated-tests/troubleshooting/failing-test/fig1.png)

The execution log also keeps information for the browser used for the run, the test, which was executed, the current version of Test Studio, etc.

### What to Look for in the Execution Log on Failure?

When a test failed, __check the failure information listed under the faulty step__. In most cases the information listed there is quite descriptive and helps you find the root cause of the failure. If we focus on the above example, it says the element in  step 5. <a href="/automated-tests/troubleshooting/element-not-found" target="_blank">cannot be found on page</a>. On top of this the element's find expression is listed, if the image search was used, and at the bottom you can even find a link to the documentation about the topic how elements are located in Test Studio.

![failure in execution log](/img/automated-tests/troubleshooting/failing-test/fig2.png)

> __Tip__
><br>
><br>
> Before you try to change the find expression for the missing element, __check the images on failure__ from the <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">Step Failure details</a> and ensure the test has reached the page you expect to find the missing element on.

## Step Failure Details

The <a href="/automated-tests/test-results/step-failure-details" target="_blank">Step Failure Details dialog</a> is only available in the case of a failing test. It provides a full stack of information to help analyzing and resolving a failing step.

### Failure Details Tab

The <a href="/automated-tests/test-results/step-failure-details#failure-tab" target="_blank">first tab</a> of these details lists the exact error, which caused the failure, and provides access to the full execution log.

![failure tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig3.png)

> __Tip__
><br>
><br>
> From this tab you can also <a href="/automated-tests/test-results/step-failure-details#how-to-export-the-step-failure-details" target="_blank">__export a zipped folder with all failure details__</a>, if you need to provide this to a colleague or the Test Studio Support team.

### Expected Vs. Actual Images Tab

The <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">__Images__ tab</a> provides a visual representation of the tested page at the time of failure. This is how you can easily sort out if the page is the one you expected - it could have changed due to an application update, or the previous steps in the test did not manage to perform correctly and navigate the page to the desired state.

![images tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig4.png)

> __Tip__
><br>
><br>
> If the page is not the expected one, but there were no recent changes in the application, probably you need to __slow down the test steps execution__, so that these can be executed when the page is ready to respond. The mechanisms in Test Studio to sync the speed of execution and application responsiveness are the <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">wait</a> and <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">verification steps</a>, and/or <a href="/features/custom-steps/execution-delay" target="_blank">execution delays</a>.

### DOM Tree On Failure

The <a href="/automated-tests/test-results/step-failure-details#page-dom-tab" target="_blank">__Page DOM__ tab</a> provides a snippet of __how Test Studio sees the DOM of the page at the time of failure__. You can inspect the overall structure of the page in the DOM, or search for particular element. It can be useful in all cases, when the failure is related to an element state - among these can be either if the element cannot be found, or is reported that does not exist, or a test times out waiting for an element, or the test targets incorrect element.

![DOM Tree tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig5.png)

> __Tip__
><br>
><br>
> If you need to explore the DOM tree in actual test runtime, you can use the <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">Visual Debugger</a>. If you need to explore the DOM tree in a recording session, you can use the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer in the Advanced Recording Tools window</a>.

### Resolve Failure

The  <a href="/automated-tests/test-results/step-failure-details#resolve-failure-tab" target="_blank">__Resolve Failure__ tab</a> from the Failure details includes a particular __suggestion tailored based on the actual error__. Therefore it will present different information for the various failures, you may encounter and you can follow the suggested steps to apply the resolution.

![Resolve Failure tab in step failure details](/img/automated-tests/troubleshooting/failing-test/fig6.png)

## Visual Debugger

The <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">Visual Debugger</a> is a useful tool, which allows you to debug a test during its execution. It appears for each quick test execution at the bottom right corner of the active display (right above the Windows system tray) and shows the progress of the executed steps. From the Visual Debugger toolbar you can <a href="/automated-tests/troubleshooting/visual-debugger#manually-pause-the-test" target="_blank">manually pause</a> the test run, or adjust its <a href="/automated-tests/troubleshooting/visual-debugger#set-auto-pause-rule-for-the-visual-debugger" target="_blank">settings to automatically pause on specific errors</a>. You can also set a breakpoint on particular step and force the test execution to pause on that step.

![Visual Debugger](/img/automated-tests/troubleshooting/failing-test/fig7.png)

Once the test is <a href="/automated-tests/troubleshooting/visual-debugger#make-use-of-the-visual-debugger-tool-options-during-test-run" target="_blank">paused in run-time</a>, you can inspect the current DOM of the page, take a snippet of the DOM and screenshot of the page, access the execution log of the steps executed so far, diagnose the current failed step, if applicable, and even report a bug in case there is a bug tracker configured for the project. Once you explore the necessary details for the failure, you can <a href="/automated-tests/troubleshooting/visual-debugger#resume-the-test-execution" target="_blank">continue the test execution</a> until the end, or with a single step run at a time. You can also choose to rerun the current step.

![Visual Debugger in Paused mode](/img/automated-tests/troubleshooting/failing-test/fig8.png)

## Test Studio Application Log

The application log is a record of log messages recorded by Test Studio throughout your interactions in the product. All records in the application log are added to indicate important events and help pinpoint where problems may occur. This log is distinct from the execution log, which only records the attempted steps and encountered exceptions during test execution. The application log is useful for unexpected occurrences such as a product crash, unexpected termination of a test run, which might prevent generating the execution log, inconsistent behavior while working with the project components.

Follow the below steps to <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">generate the logging</a> and find the error message indicating the encountered issue:

* Clear the log file;
* Ensure logging is enabled;
* Reproduce the misbehavior to be investigated;
* Once the observed inconsistency is present, open the application log from the _'View Log'_ option;
* The logging records are opened in a text editor file (usually Notepad);
* You can revise the logged messages yourself and try to find a solution based on the error message.
* Or you can contact the Test Studio Support Team and send the zipped log file via a support thread describing the experienced issue.

![Test Studio Standalone Application Log](/img/automated-tests/troubleshooting/failing-test/fig9.png)

### When to turn on the application log?

Whenever Test Studio behaves differently than expected, an application log can give more information about why. This is especially true for situations other than test failure or code compilation. For example:

- Test Studio generates error messages;
- Test Studio closes unexpectedly;
- Test Studio stops responding;
- Test Studio interacts with other software (TeamPulse, TFS, QC) differently than expected;
- A Test Studio execution browser closes unexpectedly or stops responding during execution;
- Test Studio cannot connect to a browser.

### Generating the application log

Test Studio logging options can be accessed from different components of the product. Find out how to <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">generate the application log</a> for the different installations of Test Studio.

**What to look for in the application log.**

The application log can be useful in many ways to Test Studio support engineers and developers. Users with issues should look for exceptions. 

![Log][1]

These are usually accompanied with error messages that may guide you in troubleshooting. If you are not familiar with the error message, try searching our documentation for it. If you still cannot understand the error, consider attaching a copy of the log to a <a href="/knowledge-base/best-practices-kb/submit-support-ticket" target="_blank">support ticket</a>. 

[1]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log/fig1.png