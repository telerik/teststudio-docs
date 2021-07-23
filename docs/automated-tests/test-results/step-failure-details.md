---
title: Step Failure Details
page_title: Step Failure Details
description: "Test Studio Step Failure Details. Analyze test run failure. My test studio test failed. How to fix a failed test studio test. "
position: 1
---
# Step Failure Details

The Step Failure Details dialog collects all the information related to the failed test step. This includes failure details, screenshots, and a snapshot of the DOM. The Step Failure Details section lists handy suggestion how you can resolve the specific error.

Let's use a simple test as a baseline, which navigates to bing.com and verifies the text content of the _Images_ link. The one demonstrated below is modified to look for _'ImagesModifiedToFail'_ instead of _'Images'_ so that it actually fails.

## Step Failure Details Section

<a href="/automated-tests/test-execution/quick-execution" target="_blank">Execute the sample test</a> and wait for the run to finish. The overall result of the test run is reported failed and the failing step is marked in the test. The __Step Failure Details__ section, displayed under, provides an overview of the __reason for the failure__, the __images__, and __suggestions__ what options you have to troubleshoot the error.

![Step Failure Details Section][10]

### Failure Reason Section

The __Failure Reason__ section shows a summary of the error, which caused the failure. In it you have quick access to the following details:

- [DOM tree on failure](#page-dom-tab),
- [Resolve failure suggestions](#resolve-failure-tab),
- __Copy__ button to get the error log in clipboard,
- [export the overall step failure details](#how-to-export-the-step-failure-details),
- trigger the form to submit a bug, if you have <a href="/features/integration/bug-tracking/configuration" target="_blank">configured a bug tracking tool</a> for the project.

![Failure Reason Section][11]

### Suggestions Section

The __Suggestion__ section hints you with handy features in Test Studio for __troubleshooting a failing test__ and these are based on the specific error. Among these are

- <a href="/automated-tests/troubleshooting/update-verification" target="_blank">How to update the verification definition</a>
- <a href="/automated-tests/troubleshooting/element-not-found" target="_blank">how to resolve an error for not found element</a>
- <a href="/automated-tests/troubleshooting/use-partial-run" target="_blank">How to use the partial test execution</a>
- <a href="/automated-tests/troubleshooting/use-annotated-run" target="_blank">How to trigger an annotated test execution</a>

![Suggestion Section][12]

### Images Section

The __Images__ section lists the __state of the application at the time of failure__ compared to what was captured when the test steps were recorded. The images are often useful to identify that certain step gets executed before the application is in the correct state to accept the action. Such timing issues are usually resolved by adding <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">wait steps</a> or <a href="/features/custom-steps/execution-delay" target="_blank">execution delays</a> before the action is sent towards the page.

![Suggestion Section][13]

If you click the magnifier icon, the images are opened in full size and can be zoomed.

![Suggestion Section][14]

## How to Open the Step Failure Details Window?

Execute the sample test and wait until it fails. Hover the mouse over the red cross next to the failed step - a **Step Failure Summary** will popup for a while.

![hover over the red cross][2]

Click on the red cross to open the overall **Step Failure Details** with possible options to resolve the encountered error.

![Click the red cross to open the failure details dialog][2a]

## What to Look for in the Step Failure Details?

The failure dialog provides a variety of useful details, which can be used for the different failure scenarios, divided in few tabs. Let's have an overview for each of these tabs and how these can help us find the solution for the failing step.

### Failure Tab

The **'Failure'** tab provides a summarized information for the encountered error - sometimes this can be quite descriptive, and other times it could be more generic.

![The failure tab][3]

From this view you can also access other useful options:

* **View Exception Details**: lists the log for the failed test step only.

* **Complete Test Log**: displays the entire test log in the format of the quick execution log.

* **Copy**: copies the exception details for the failed step to the clipboard to paste into another application.

* **Export**: saves a zipped file containing a text file with the failed step log, the complete test log, a screenshot of the web page when the failure occurred, and a snapshot of the DOM tree in XML form.

* **Submit Bug**: loads the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and logs a bug, if you have configured a bug tracking application.

* **Resolve**: navigates to the ***'Resolve Failure'*** tab, where you will get suggestions to apply a fix depending on the error.

### Images Tab

The **'Images'** tab displays two screenshots of the browser: the state at time of failure and the expected state. Storyboard must be enabled in <a href="/features/project-settings/recording-options" target="_blank">Project Settings</a> for the expected state image to appear.

![Images tab][4]

### Page DOM Tab

The **'Page DOM'** tab displays a snapshot of the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-dom-on-failure" target="_blank">DOM state</a> at the time of failure. You can use it to locate the element in the DOM tree and check its state, content, etc.

![Page DOM tab][5]

**When to use the DOM on Failure?**

The DOM on Failure is most helpful in situations where a test does not properly locate and act on a particular element. This includes any of the following, when unexpected:

- 'Element does not exist' exceptions;
- 'Element not found' exceptions;
- 'Timed out waiting for element' exceptions;
- Test execution targets incorrect element.

**What to look for in the DOM on Failure?**

The DOM on Failure provides a record of the elements that Test Studio could see in the browser at the time the test failed. Compare with <a href="/features/elements-explorer/find-element" target="_blank">the find logic</a> of the element that Test Studio expects to be in the browser during the failed step. This helps to identify which element should have been targeted, why the incorrect element may have been targeted, or what state the browser may have been in instead of the correct state.

### Resolve Failure Tab

The **'Resolve Failure'** tab provides the opportunity to identify and correct the issue that caused the failure. For validation steps, the Sentence Verification Builder allows you to reload the page, make changes to the verification sentence, and re-run the verification until the verification passes.

![Resolve Failure tab][6]

In case the failure is caused by an element, which cannot be located on the page, the **'Resolve Failure'** tab provides different options to <a href="/features/elements-explorer/find-element" target="_blank">change the elements find expression</a>.

![Resolve Failure tab missing element][7]

If the element was located on the page using the backup search recorded for it, you can directly choose the **'Troubleshoot'** button. You can choose between the automatic update of search criteria used, or manually select a new element.

![Resolve Failure tab missing element troubleshoot][8]

## How to Export the Step Failure Details?

When a test is failing and you need to share the identified faulty behavior with a team mate, developer, or the Test Studio Support team, you can easily __export the complete set of failure details into a single zipped file__. The archive contains the failed step log, the complete test execution log, a screenshot of the web page and a snapshot of the DOM tree at the time of failure. To get the zipped file, click on the __Export__ button on the _Failure_ tab and choose a folder where to store it.

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