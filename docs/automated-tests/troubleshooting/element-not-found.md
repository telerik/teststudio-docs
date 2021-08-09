---
title: How to Troubleshoot Element Not Found 
page_title: How to Troubleshoot Element Not Found?
description: "Learn how to debug the element not found error in Test Studio. How to understand what causes the test to fail and what troubleshoot approach to take when your test fails to locate an element on page." 
position: 1
---
# Troubleshoot 'Element Not Found' Error

A common failure when executing Test Studio tests is that a particular element is not found on the page during the test run.

In some cases, the element is visibly available on the page but still reported as not found by Test Studio. This tutorial will guide you through the troubleshooting workflow for this type of failure and what can be causing it.

## Record the Test Scenario

In this tutorial, we will use a sample login application. The task is to fill in the login credentials and click on the _Log In_ button. After logging in, we get a _Welcome, Test Studio_ greeting.

![sample app](/img/automated-tests/troubleshooting/element-not-found/1SampleApp.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder and recorded</a> the following test steps:

![Recorded test](/img/automated-tests/troubleshooting/element-not-found/2RecordedTest.png)

These are the individual steps in the sample scenario:

* Navigate to the sample login application.
* Build a couple of verifications to ensure the loaded page is the correct one, and there is no user already logged in.
* Enter the login credentials.
* Click the __Log In__ button.
* Verify the user is successfully logged in.

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution of this sample test</a>, we expect it to pass successfully. However, step 4., which enters the username, is failing for some reason:

![Failing test](/img/automated-tests/troubleshooting/element-not-found/3FailingTest.png)

Looking at the <a href="/automated-tests/test-results/step-failure-details" target="_blank">step failure details</a> and the <a href="/automated-tests/test-results/step-failure-details#images-section" target="_blank">images</a>, we can clearly see the correct page is loaded, the element is there, but the test failed with the following failure reason:

```
Attempting to find [Html] element using Find logic  (Html): 
[id 'Exact' e83f05e5-13b9-629d-edb3-99719f8515ce] AND [tagname 'Exact' input]
Unable to locate element. Search failed!
```

## Troubleshoot the 'Element Not Found' Error

To check the <a href="/automated-tests/elements/elements-find-expression" target="_blank">find expression of the element</a>, which cannot be found, click on the failing step 4. In <a href="/automated-tests/elements/overview" target="_blank">Test Studio’s Elements Explorer</a>, the step's target element is marked with a red arrow.

Right-click the highlighted element and choose <a href="/automated-tests/elements/find-element#edit-the-find-expression-of-an-element" target="_blank">__Edit Element__</a> from the context menu:

![Edit Element](/img/automated-tests/troubleshooting/element-not-found/4EditElement.png)

The element is opened in _Edit mode_ and the <a href="/automated-tests/elements/find-element#options-in-element-pane-without-active-recording-session" target="_blank">options for starting a debugging session</a> are listed in the __Edit in Live__ section of the _Elements_ ribbon. Choose the __Run to Test Step__ button for this troubleshooting session.

![Edit in Live](/img/automated-tests/troubleshooting/element-not-found/5EditinLive.png)

This runs the test up to the failing step and launches the Test Studio Recorder. The page DOM is loaded, and the find expression is validated. In the current example, the id filter for the _UsernameInput_ element is highlighted, and this seems to be the issue with finding the element in test run-time.

When we refer to <a href="/automated-tests/elements/find-element#options-in-element-pane-with-active-recording-session" target="_blank">the DOM tree of the live page</a>, we clearly see that the id attribute of the input element has a different value than the one stored in our find expression:

![Element in DOM with dynamic Id](/img/automated-tests/troubleshooting/element-not-found/6DynamicId.png)

Click the __Update Filters__ button to replace the id in the find expression with the current value from the DOM tree. However, this is very likely to fail on the next test execution because the id attribute of the input element is dynamically generated.

The Test Studio find expression builder lists all attributes of the opened element, and any of these can be added in the find expression. If we look closely at the _input_ element, we see that its __name__ attribute is unique and, if it is used in the find expression instead of the __id__, finding the element in test runtime gets more robust.

```HTML
<input class="form-control" type="text" placeholder="User Name" name="UserName" id="2208d540-2a45-1e2b-6b8c-a00958f16e85">
```

Remove the __id__ filter from the current find expression and add the __name__ filter instead.

![Validate Find Expression](/img/automated-tests/troubleshooting/element-not-found/7ValidateExpression.png)

Click the __Validate Expression__ button to validate that the new find expression points to the correct element on the page.

The find expression for the __password input__ element also uses the dynamic __id__ attribute, and you need to modify it by following the same steps. The test with modified find expressions for the element passes successfully.

![Test Passes after Changes](/img/automated-tests/troubleshooting/element-not-found/8TestPasses.png)