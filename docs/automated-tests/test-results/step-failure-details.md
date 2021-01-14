---
title: Step Failure Details
page_title: Step Failure Details
description: "Test Studio Step Failure Details. Analyze test run failure. My test studio test failed. How to fix a failed test studio test. "
position: 1
---
# Step Failure Details

The Step Failure Details dialog collects all the information related to the failed test step. This includes failure details, screenshots, and a snapshot of the DOM. For some of the possible failures you can find resolution suggestions directly from the dialog.

Let's use a very simple test as a baseline, which navigates to bing.com and verifies the text content of the _Images_ link. The one demonstrated below is modified to look for _'ImagesModifiedToFail'_ instead of _'Images'_ so that it actually fails.

## How to Open the Step Failure Details?

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

### Resolve Failure Tab

The **'Resolve Failure'** tab provides the opportunity to identify and correct the issue that caused the failure. For validation steps, the Sentence Verification Builder allows you to reload the page, make changes to the verification sentence, and re-run the verification until the verification passes.

![Resolve Failure tab][6]

In case the failure is caused by an element, which cannot be located on the page, the **'Resolve Failure'** tab provides different options to <a href="/features/elements-explorer/find-element" target="_blank">change the elements find expression</a>.

![Resolve Failure tab missing element][7]

If the element was located on the page using the backup search recorded for it, you can directly choose the **'Troubleshoot'** button. You can choose between the automatic update of search criteria used, or manually select a new element.

![Resolve Failure tab missing element troubleshoot][8]

[1]: /img/automated-tests/test-results/step-failure-details/fig1.png
[2]: /img/automated-tests/test-results/step-failure-details/fig2.png
[2a]: /img/automated-tests/test-results/step-failure-details/fig2a.png
[3]: /img/automated-tests/test-results/step-failure-details/fig3.png
[4]: /img/automated-tests/test-results/step-failure-details/fig4.png
[5]: /img/automated-tests/test-results/step-failure-details/fig5.png
[6]: /img/automated-tests/test-results/step-failure-details/fig6.png
[7]: /img/automated-tests/test-results/step-failure-details/fig7.png
[8]: /img/automated-tests/test-results/step-failure-details/fig8.png