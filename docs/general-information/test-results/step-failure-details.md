---
title: Step Failure Details
page_title: Step Failure Details
description: "Test Studio Step Failure Details. Analyze test run failure. My test studio test failed. How to fix a failed test studio test. "
position: 3
---
# Step Failure Details

The Step Failure Details dialog collects all the information related to a single failed test step. This includes failure details, screenshots, and a snapshot of the DOM. You can even resolve the failure directly from the dialog.

In the example below, step three has failed. Hover over the red cross next to the failed step to see the **Step Failure Summary**. Click it to open more detailed **Step Failure Details** with options to resolve the error.

![Test][2]

## Failure Tab

The **'Failure'** tab displays the test name, the test step description, and a summary of what caused the step to fail. Step three is verifying that the TextContent of an href element on the page exactly matches the string *'Images123'*. It does not match; the actual value is *'Images'*, thus the verification step fails.

* **View Exception Details**: lists the log for the failed test step.

* **Complete Test Log**: displays the entire log.

* **Copy**: copies the exception details for the failed step to the clipboard to paste into another application.

* **Export**: saves a zipped file containing a text file with the failed step log, the complete test log, a screenshot of the web page when the failure occurred, and a snapshot of the DOM tree in XML form.

* **Submit Bug**: loads the <a href="/features/integration/bug-tracking/submit-bug" target="_blank">Submit Bug</a> dialog and log a bug in your previously configured bug tracking application.

* **Resolve**: navigates to the *'Resolve Failure'* tab, where you will get suggestions to apply a fix depending on the error.

![Step failure details][3]

## Images Tab

The **'Images'** tab displays two screen shots of the browser: the state at time of failure and the expected state. Storyboard must be enabled in <a href="/features/project-settings/recording-options" target="_blank">Project Settings</a> for the expected state image to appear.

![Images tab][4]

## Page DOM Tab

The **'Page DOM'** tab displays a tree view of the page's <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-dom-on-failure" target="_blank">DOM state</a> at the time of failure.

![Page DOM tab][5]

## Resolve Failure Tab

The **'Resolve Failure'** tab provides the opportunity to identify and correct the issue that caused the failure. For validation steps, the Sentence Verification Builder allows you to reload the page, make changes to the verification sentence, and re-run the verification until the verification passes.

![Resolve Failure tab][6]

In case the failure is caused by an element, which cannot be located on the page, the **'Resolve Failure'** tab provides different options to <a href="/features/elements-explorer/find-element" target="_blank">change the elements find expression</a>.

![Resolve Failure tab missing element][7]

If the element was located on the page using the backup search recorded for it, you can directly choose the **'Troubleshoot'** button. You can choose between the automatic update of search criteria used, or manually select a new element.

![Resolve Failure tab missing element troubleshoot][8]

[1]: /img/general-information/test-results/step-failure-details/fig1.png
[2]: /img/general-information/test-results/step-failure-details/fig2.png
[3]: /img/general-information/test-results/step-failure-details/fig3.png
[4]: /img/general-information/test-results/step-failure-details/fig4.png
[5]: /img/general-information/test-results/step-failure-details/fig5.png
[6]: /img/general-information/test-results/step-failure-details/fig6.png
[7]: /img/general-information/test-results/step-failure-details/fig7.png
[8]: /img/general-information/test-results/step-failure-details/fig8.png