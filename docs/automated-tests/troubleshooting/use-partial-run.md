---
title: Use Partial Test Run
page_title: How to Use Partial Test Run to Troubleshoot?
description: "Use the Test Studio feature to execute only part of a test. Partial test execution allows you to run only certain steps from a test and continue recording steps from that point." 
position: 4
---
# Use Partial Test Runs to Troubleshoot a Failure

In many cases it is quite useful to execute only part of a test - when you need to insert few new steps in the middle of a test, or when you need to debug a failing step. Test Studio provides solution for these cases with its powerful ability to combine the test execution of few steps and leave the page in that state in recording session.

Let’s take a look at this useful feature with the following example and practical demonstration.

## Record the Scenario

For this tutorial we use a sample application. The task is to load the sample page and to verify a _button_ is enabled.

![Sample web app](/img/automated-tests/troubleshooting/use-partial-run/1Scenario.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder and recorded</a> the following test steps:

![Steps in test](/img/automated-tests/troubleshooting/use-partial-run/2RecordedTest.png)

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution of this sample test</a>, we expect it to pass successfully. However, the __verification in step 2. fails__ and the failure message clearly states that the ___button_ state is not enabled__. The _Images_ section shows that the correct page is loaded, which brings no hint for identifying the cause of the failure.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/3Failingtest.png)

This is where the <a href="/automated-tests/test-execution/partial-test-execution#run-to-here" target="_blank">__Run to Here__ feature</a> comes into action. The partial test run can be triggered from the context menu of a selected step - right click on the failing step and choose __Run -> To Here__.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/4RuntoHere.png)

Choosing this option launches a new instance of the selected (or if set, <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">preferred</a>) browser, __execute the test to the selected step, leave the browser open and the application in its current state and attaches the recorder__. The test run fails again, but there is an active recorder session running for this browser instance. That enables the other partial run options in the step context menu - to run <a href="/automated-tests/test-execution/partial-test-execution#run-selected-steps" target="_blank">__Selected Steps__</a> or to continue the run <a href="/automated-tests/test-execution/partial-test-execution#run-from-here" target="_blank">__From Here__</a>.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/5RunSelected.png)

Click on the failing step 2. and choose to run only this step in the already loaded page. This time the step passes successfully.

![Failure in test](/img/automated-tests/troubleshooting/use-partial-run/6Step2passing.png)

Take a closer look at the execution log generated after executing only the failing step - the ___Navigate_ step (step 1.) is not executed__ for this partial run, because __Run->Selected Steps__ is used. The __verification step for the state of the button (step 2.) now passes successfully__, when the page was already loaded. This a sure sign that the verification (or action) from step 2. was __executed too fast and the page was not completely loaded__.

In similar scenarios you can use <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">__wait steps__</a> or <a href="/features/custom-steps/execution-delay" target="_blank">__execution delays__</a>, which will help in __synchronizing the speed of the test steps execution and the page under test responsiveness__. Using such steps in between the action steps significantly improves the stability and consistency of test execution.

Once execution delay is added and the complete test is executed, the verification step successfully checks the state of the _button_ element on the page.

![successful test with execution delay](/img/automated-tests/troubleshooting/use-partial-run/7TestPassing.png)