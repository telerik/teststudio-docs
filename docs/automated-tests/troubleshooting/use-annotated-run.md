---
title: Use the Annotations for Troubleshooting
page_title: How to Use the Annotations for Troubleshooting Failing Test?
description: "Use the Test Studio feature to execute a test with annotations to troubleshoot a failing test and debug the errors, which caused it. My test fails and I am not sure what causes the error." 
position: 0
---
# Use the Annotated Run for Troubleshooting Failures

Quick test execution can be quite handy for debugging purposes, especially when using the feature to toggle on annotations during the run. When enabled, the annotations highlight the target element of each executed step along with a brief message. They are helpful in cases when the sequence of actions cannot be followed and may reveal the reason why a test does not behave as intended.

The below article describes an end to end scenario, when the quick execution with annotations can be helpful.

## Record the Scenario

For this tutorial we use a sample application. The task is to click on the _Impressive_ radio button and then verify that the word _Impressive_ is displayed in green in the confirmation.

![Sample web app](/img/automated-tests/troubleshooting/use-annotated-run/1WebApp.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder and recorded</a> the following test steps:

![Steps in test](/img/automated-tests/troubleshooting/use-annotated-run/2RecordedTest.png)

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution of this sample test</a>, we expect it to pass successfully. However, the verification in step 3. fails, even though step 2., which performs the click action on the _Impressive_ radio button is reported as successfully executed.

![Failure in test](/img/automated-tests/troubleshooting/use-annotated-run/3StepFails.png)

The standard troubleshooting implies to refer the <a href="/automated-tests/test-results/step-failure-details" target="_blank">step failure details</a> for more information and you can see the following failure reason is displayed:

```
Unable to locate element by Find Expression!
Attempting to find [Html] element using 
Find logic 
 (Html): [tagname 'Exact' span] AND [TextContent 'Exact' Impressive]
Unable to locate element. Search failed!
```

Based on this failure message, Test Studio is looking for a span element with _Text Content Impressive_. As the find expression seems to be pointing to a specific element, Test Studio should not have a problem locating the element.

Therefore, the next suggestion is that probably not the right page was loaded during the test execution. In this case the <a href="/automated-tests/test-results/step-failure-details#images-tab" target="_blank">images from the failure details</a>, which Test Studio records for expected state of the page and the state at the time of failure, should help in the investigation of this error. When we check the images, though, these show the correct page was loaded at the time of failure:

![step failure details](/img/automated-tests/troubleshooting/use-annotated-run/4StepFailureDetails.png)

In such case, the next step in the troubleshooting process is to <a href="/automated-tests/test-execution/quick-run-annotations" target="_blank">turn on the annotations</a> and observe the execution. The annotations can be enabled from the Quick Execute section in the Test Studio ribbon:

![Enable Annotations](/img/automated-tests/troubleshooting/use-annotated-run/5EnableAnnotations.png)

The value of 400 (in miliseconds) is the delay between the annotations, this is the default value and should be perfectly enough for observing the execution. If needed the delay can be adjusted. The Execute button should be clicked in order to start the annotated test execution:

![Start Execution](/img/automated-tests/troubleshooting/use-annotated-run/6ExecuteButton.png)

The annotated run reveals quite useful information. Step 2 is passing successfully because a mouse click is actually performed, but it is sent slightly below the _Impressive_ radio button and this should be the reason why the verification fails.

![Click step misclicked the correct element](/img/automated-tests/troubleshooting/use-annotated-run/7AnnotatedClick.png)

An easy solution for this problem will be to record the click step again. Once re-recorded the test executes successfully.

![Successful test](/img/automated-tests/troubleshooting/use-annotated-run/8TestPasses.png)