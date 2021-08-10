---
title: Use Partial Test Run
page_title: How to Use Partial Test Run to Troubleshoot
description: "Use the Partial Test Run feature in Test Studio to execute only a test segment. Partial test execution allows you to run only certain steps from a test and continue recording steps from that point." 
position: 4
---
# Use Partial Test Runs to Troubleshoot a Failure

Sometimes you need to execute only part of a test - when you need to insert few new steps in the middle of a test, or when you need to debug a failing step. The solution is the partial test run feature.

This article is a practical demonstration of the partial test run.

## Record the Scenario

In this tutorial, we use a sample application. The task is to load the sample page and verify that a _button_ is `enabled`.

![Sample web app](/img/automated-tests/troubleshooting/use-partial-run/1Scenario.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder</a> and recorded the following test steps:

![Steps in test](/img/automated-tests/troubleshooting/use-partial-run/2RecordedTest.png)

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution</a> of this sample test, we expect it to pass successfully. However, the verification in step 2 fails, and the failure message states that the button's state is not `enabled`. The _Images_ section shows that the correct page is loaded, which gives us no hints for the cause of the failure.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/3Failingtest.png)

The <a href="/automated-tests/test-execution/partial-test-execution#run-to-here" target="_blank">__Run to Here__ feature</a> allows you to troubleshoot similar scenarios. You can trigger the partial test run from the context menu of a selected step - right-click the failing step and choose __Run > To Here__.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/4RuntoHere.png)

Choosing this option launches a new instance of the selected browser, executes the test up to the selected step, leaves the browser open and the application in its current state, and attaches the recorder. The test run fails again, but an active recorder session is running for this browser instance. This enables more partial run options in the step's context menu - to run <a href="/automated-tests/test-execution/partial-test-execution#run-selected-steps" target="_blank">__Selected Steps__</a> or to continue the run <a href="/automated-tests/test-execution/partial-test-execution#run-from-here" target="_blank">__From Here__</a>.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/5RunSelected.png)

Click the failing step 2 and choose to run only this step on the already loaded page. This time the step passes successfully.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/6Step2passing.png)

Take a closer look at the execution log generated after executing only the failing step - the __Navigate__ step is not executed for this partial run because __Run > Selected Steps__ is used. Now that the page has already been loaded, the verification step for the state of the button (step 2) passes successfully - a sure sign that the verification (or action) in step 2 has been executed too early and the page hasn't been completely loaded.

In similar scenarios, you can use <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">__wait steps__</a> or <a href="/features/custom-steps/execution-delay" target="_blank">__execution delays__</a>, which help in adjusting the speed of the test steps execution to the responsiveness of the tested page. Using such steps in between the action steps significantly improves the stability and consistency of the test execution.

Once an execution delay is added and the complete test is executed, the verification step successfully checks the state of the _button_ element on the page.

![successful test with execution delay](/img/automated-tests/troubleshooting/use-partial-run/7TestPassing.png)