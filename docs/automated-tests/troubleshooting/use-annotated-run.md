---
title: Use the Annotations for Troubleshooting
page_title: How to Use the Annotations for Troubleshooting Failing Test?
description: "Use the Test Studio feature to execute a test with annotations to troubleshoot a failing test and debug the errors, which caused it. My test fails and I am not sure what causes the error." 
position: 3
---
# Use the Annotated Run for Troubleshooting Failures

The quick test execution can be quite handy for debugging purposes, especially when using the feature to toggle on annotations during the run. When enabled, the annotations highlight the target element of each executed step along with a brief message. They are helpful in cases when the sequence of actions cannot be followed and may reveal the reason why a test does not behave as intended.

This article describes a complete scenario that demonstrates how the quick test execution with annotations can be helpful.

## Record the Scenario

For this tutorial, we use a sample application. The task is to click the _Impressive_ radio button and then verify that the word _Impressive_ is displayed in green in the confirmation message.

![Sample web app](/img/automated-tests/troubleshooting/use-annotated-run/1WebApp.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder and recorded</a> the following test steps:

![Steps in test](/img/automated-tests/troubleshooting/use-annotated-run/2RecordedTest.png)

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution of this sample test</a>, we expect it to pass successfully. However, the verification in step 3 fails, even though step 2, which performs the click action on the _Impressive_ radio button, is reported as successfully executed.

![Failure in test](/img/automated-tests/troubleshooting/use-annotated-run/3StepFails.png)

The standard troubleshooting implies reviewing the <a href="/automated-tests/test-results/step-failure-details" target="_blank">Step Failure Details</a> for more information:

```
Unable to locate element by Find Expression!
Attempting to find [Html] element using 
Find logic 
 (Html): [tagname 'Exact' span] AND [TextContent 'Exact' Impressive]
Unable to locate element. Search failed!
```

Based on this message, you find out that Test Studio is looking for a _span_ element with _Text Content_, which is exactly _Impressive_. As the find expression seems to be pointing to a specific element, Test Studio should not have trouble locating the element, and this doesn't look like the reason for the failure.

The next suggestion is that the page loaded during the test run, may not be the right one. In this case, the images in the <a href="/automated-tests/test-results/step-failure-details#images-section" target="_blank">Step Failure Details</a>, which Test Studio records for the expected state of the page and the state at the time of failure, should help in the investigation of this error. When we check the images, though, these show that the correct page is loaded, but the confirmation message about the selected option is not present on the page.

![step failure details](/img/automated-tests/troubleshooting/use-annotated-run/4StepFailureDetails.png)

The findings from the images at the time of failure suggest that the preceding step (step 2) was not executed as expected. Step 2 should click the _Impressive_ radio button. In such cases, the next recommended step in the troubleshooting process is to <a href="/automated-tests/test-execution/quick-run-annotations" target="_blank">turn on the annotations</a> and observe the quick execution. You can enable the annotations in the **Quick Execute** section of Test Studio's ribbon.

![Enable Annotations](/img/automated-tests/troubleshooting/use-annotated-run/5EnableAnnotations.png)

Next to the __Annotations__ toggle button, you can see the value of `400` (in milliseconds) - this is the delay between the actions performed during each step. It is used to display the short annotation messages for each step. The default value is usually enough for good visibility of the step actions during the test execution. The 400 milliseconds delay can be adjusted if necessary.

Hit the __Execute__ button to start the annotated test execution.

![Start Execution](/img/automated-tests/troubleshooting/use-annotated-run/6ExecuteButton.png)

The annotated run reveals quite useful information. Step 2 is marked as successfully passing because a mouse click is actually performed. But with the help of the annotated highlighted elements, you can see that the action is sent slightly below the _Impressive_ radio button. This misclick doesn't trigger the confirmation that an option was selected, and the verification in step 3 cannot locate the element, which represents the confirmation message.

![Click step misclicked the correct element](/img/automated-tests/troubleshooting/use-annotated-run/7AnnotatedClick.png)

An easy solution for this problem will be to record the click step again. Once re-recorded, the test executes successfully.

![Successful test](/img/automated-tests/troubleshooting/use-annotated-run/8TestPasses.png)