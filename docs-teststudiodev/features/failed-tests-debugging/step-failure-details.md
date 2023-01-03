---
title: Step Failure Details
page_title: Step Failure Details - Test Studio Dev Documentation
description: The Step Failure Details dialog collects all the information related to a single failed test step during Test Studio Dev Execution.
position: 0
---
# Step Failure Details

The Step Failure Details dialog collects all the information related to a single failed test step. This includes failure details, screenshots, and a snapshot of the DOM. You can even resolve the failure directly from the dialog.

In the example below, step four has failed. Double-click ![step failure icon][1] next to the failed step to load the **Step Failure Details** dialog.

![Test][2]

## Failure Tab

The Failure tab displays the test name, the test step description, and a summary of what caused the step to fail. Step four is verifying that the TextContent exactly matches the string Purple. It does not match; the actual value is Telerik, thus the Verification fails.

* **View Exception Details**: lists the log for the failed test step.

* **Complete Test Log**: displays the entire log.

* **Copy**: copies the exception details for the failed step to the clipboard to paste into another application.

* **Export**: saves a zipped file containing a text file with the failed step log, the complete test log, a screenshot of the web page when the failure occurred, and a snapshot of the DOM tree in XML form.

* **Submit Bug**: the feature is integrated in the <a href="https://www.telerik.com/teststudio" target="_blank">Ultimate version of Test Studio</a> only.

* **Resolve**: navigates to the Resolve Failure tab where you can fix element location errors.

![Step failure details][3]

## Image Tab

The Image tab displays two screen shots of the browser: the state at time of failure and the expected state. Storyboard must be enabled in <a href="/features/project-settings/recording-options" target="_blank">Project Settings</a> for the expected state image to appear.

![Image tab][4]

## Page DOM Tab

The Page DOM tab displays a tree view of the page's <a href="/features/failed-tests-debugging/using-the-dom-on-failure" target="_blank">DOM state</a> at the time of failure.

![Page DOM tab][5]

## Resolve Failure Tab

The Resolve Failure tab provides the opportunity to identify and correct the issue that caused the failure. For validation steps, the Sentence Verification Builder allows you to reload the page, make changes to the verification sentence, and re-run the verification until the verification passes.

![Resolve Failure tab][6]

[1]: images/step-failure-details/fig1.png
[2]: images/step-failure-details/fig2.png
[3]: images/step-failure-details/fig3.png
[4]: images/step-failure-details/fig4.png
[5]: images/step-failure-details/fig5.png
[6]: images/step-failure-details/fig6.png