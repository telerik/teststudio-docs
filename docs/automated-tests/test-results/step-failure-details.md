---
title: Step Failure Details
page_title: Step Failure Details
description: "Test Studio Step Failure Details. Analyze test run failure. My test studio test failed. How to fix a failed test studio test. "
position: 1
---
# Step Failure Details

The __STEP FAILURE DETAILS__ dialog displays all the information related to the failed test step: failure reason, screenshots, and a snapshot of the DOM. It also provides handy suggestions on how to resolve the specific error.

To demonstrate the failure details dialog, let's use a sample test, which navigates to bing.com and verifies the text content of the _Images_ link. The one demonstrated below is modified to look for _'ImagesModifiedToFail'_ instead of _'Images'_ so that it actually fails.

## Step Failure Details Dialog

<a href="/automated-tests/test-execution/quick-execution" target="_blank">Execute the sample test</a> and wait for the run to finish. The overall result from the test run is __Fail__, and the failing step is marked in the test. The __Step Failure Details__ section provides an overview of the failure reason, the images, and suggestions about troubleshooting the error.

![Step Failure Details Section][10]

### Failure Reason Section

The __Failure Reason__ section shows a summary of the error, which caused the failure. It provides a quick access to the following:

- [__Page DOM__](#page-dom-tab)&mdash;Displays the DOM state at the time of the failure.
- [__Resolve Failure__](#resolve-failure-tab)&mdash;Suggestions on how to identify the cause.
- __Copy__&mdash;Copies the error log to the clipboard.
- [__Export__](#how-to-export-the-step-failure-details)&mdash;Exports the overall step failure details.
- __Submit bug__&mdash;Triggers the form to submit a bug report, if you have <a href="/features/integration/bug-tracking/configuration" target="_blank">configured a bug tracking tool</a> for the project.

![Failure Reason Section][11]

### Suggestions Section

The __Suggestions__ section hints you with handy Test Studio features for troubleshooting a failing test. These hints are based on the specific error, for example:

- <a href="/automated-tests/troubleshooting/update-verification" target="_blank">How to update the verification definition</a>.
- <a href="/automated-tests/troubleshooting/element-not-found" target="_blank">How to resolve an error for not found element</a>.
- <a href="/automated-tests/troubleshooting/use-partial-run" target="_blank">How to use the partial test execution</a>.
- <a href="/automated-tests/troubleshooting/use-annotated-run" target="_blank">How to trigger an annotated test execution</a>.

![Suggestion Section][12]

### Images Section

The __Images__ section displays the state of the application at the time of failure and compares it to what was captured when the test steps were recorded. The images are often useful to identify that a certain step gets executed before the application is in the correct state to accept the action. You can resolve such timing issues by adding <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">wait steps</a> or <a href="/features/custom-steps/execution-delay" target="_blank">execution delays</a> before the action is sent towards the page.

![Suggestion Section][13]

If you click the magnifier icon, the images are opened in full size and can be zoomed.

![Suggestion Section][14]

## How to Open the Step Failure Details Window?

Execute the [sample test](#step-failure-details) and wait until it fails. Hover the mouse over the red cross next to the failed step - a **Step Failure Summary** will pop up for a while.

![hover over the red cross][2]

Click the red cross to open the overall **Step Failure Details** with possible options to resolve the encountered error.

![Click the red cross to open the failure details dialog][2a]

## What to Look for in the Step Failure Details?

The failure dialog provides plenty of information grouped in tabs. The following sections describe the tabs and their usage.

### Failure Tab

The **Failure** tab provides a summary about the encountered error - sometimes this can be quite descriptive, and other times it could be more generic.

![The failure tab][3]

From this view you can also access other useful options:

* **View Exception Details**&mdash;Lists the log only for the failed test step.

* **View Complete Test Log**&mdash;Displays the entire test log in the format of the quick execution log.

* **Copy**&mdash;Copies the exception details for the failed step to the clipboard, so you can paste it into another application.

* **Export**&mdash;Saves a zipped file containing a text file with the failed step log, the complete test log, a screenshot of the web page when the failure occurred, and a snapshot of the DOM tree in XML form.

* **Submit Bug**&mdash;Loads the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and logs a bug, if you have configured a bug tracking application.

* **Resolve**&mdash;Navigates to the **Resolve Failure** tab, where you will get suggestions to apply a fix depending on the error.

### Images Tab

The **Images** tab displays two screenshots from the browser: the state at time of failure and the expected state. Storyboard must be enabled in the <a href="/features/project-settings/recording-options" target="_blank">Project Settings</a> for the expected state image to appear.

![Images tab][4]

### Page DOM Tab

The **Page DOM** tab displays a snapshot of the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-dom-on-failure" target="_blank">DOM state</a> at the time of failure. You can use it to locate the element in the DOM tree and check its state, content, etc.

![Page DOM tab][5]

#### When to Use the DOM on Failure?

The **Page DOM** is most helpful in situations where a test does not properly locate and act on a particular element. This includes any of the following, when unexpected:

- 'Element does not exist' exceptions.
- 'Element not found' exceptions.
- 'Timed out waiting for element' exceptions.
- Test execution targets incorrect element.

#### What to Look for in the DOM on Failure?

The DOM on Failure provides a record of the elements that Test Studio could see in the browser at the time when the test failed. Compare it with <a href="/features/elements-explorer/find-element" target="_blank">the find logic</a> of the element that Test Studio expects to be in the browser during the failed step. This helps to identify which element should have been targeted, why the incorrect element may have been targeted, or what state the browser may have been in instead of the correct state.

### Resolve Failure Tab

The **Resolve Failure** tab provides the opportunity to identify and correct the issue that caused the failure. For validation steps, the Sentence Verification Builder allows you to reload the page, make changes to the verification sentence, and re-run the verification until the verification passes.

![Resolve Failure tab][6]

In case the failure is caused by an element that cannot be located on the page, the **Resolve Failure** tab provides different options to <a href="/features/elements-explorer/find-element" target="_blank">change the element's find expression</a>.

![Resolve Failure tab missing element][7]

If the element was located on the page by using the element's recorded backup search, you can choose the **Troubleshoot** button. You can choose between the automatic update of search criteria used or manually select a new element.

![Resolve Failure tab missing element troubleshoot][8]

## How to Export the Step Failure Details?

When a test is failing and you need to share the identified faulty behavior with a teammate, developer, or the Test Studio Support team, you can export the complete set of failure details into a single zipped file. The archive contains the failed step log, the complete test execution log, a screenshot of the web page, and a snapshot of the DOM tree at the time of failure. To get the zipped file, click the __Export__ button in the __Failure__ tab and choose a folder to save it.

![Export the step failure details][9]

[10]: /img/automated-tests/test-results/new-step-failure-details/new1.png
[11]: /img/automated-tests/test-results/new-step-failure-details/new2.png
[12]: /img/automated-tests/test-results/new-step-failure-details/new3.png
[13]: /img/automated-tests/test-results/new-step-failure-details/new4.png
[14]: /img/automated-tests/test-results/new-step-failure-details/new5.png

[1]: /img/automated-tests/test-results/step-failure-details/fig1.png
[2]: /img/automated-tests/test-results/new-step-failure-details/fig2.png
[2a]: /img/automated-tests/test-results/new-step-failure-details/fig2a.png
[3]: /img/automated-tests/test-results/step-failure-details/fig3.png
[4]: /img/automated-tests/test-results/step-failure-details/fig4.png
[5]: /img/automated-tests/test-results/step-failure-details/fig5.png
[6]: /img/automated-tests/test-results/step-failure-details/fig6.png
[7]: /img/automated-tests/test-results/step-failure-details/fig7.png
[8]: /img/automated-tests/test-results/step-failure-details/fig8.png
[9]: /img/automated-tests/test-results/step-failure-details/fig9.png