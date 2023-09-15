---
title: Review the Results and Debug Test Failures
page_title: Review the Results and Debug Test Failures
description: "View the results from your execution and analyze the passed and failed steps. Debug Test Failures"
position: 4
---
# Review The Results and Debug Test Failures

Test Studio provides a good visual representation of executed tests and steps in a single glance. Along with that there are multiple useful tools, which allow you to easily modify the test steps and elements in order to fix any errors. In this article you can find details about the below listed features of Test Studio.

- [Quick Run Execution log](#quick-run-execution-log)
- [Step failure details](#step-failure-details)
- [Visual debugger](#visual-debugger)
- [Partial Test Execution](#partail-test-execution)
- [Annotated Test Run](#annotated-test-run)
- [Application log](#application-log)
- [Analyze test list results](#analyze-test-list-results)

<br><br>
<div><a href="/getting-started/first-execution">Back to <strong>Execute Your First Test</strong></a><a style="float:right" href="/getting-started/next-steps">Go to <strong>Next Steps</strong></a></div>
<br><br>

## Quick Run Execution Log

The <a href="/general-information/test-results/analyze-quick-run-results" target="_blank">quick execution log</a> is generated in the test view after a <a href="/general-information/test-execution/quick-execution" target="_blank">quick test run</a>. It contains details about the last run of the current test and you can open it by clicking on the **View Log** button.

![View log][1]

## Step Failure Details Dialog

The results generated from a <a href="/general-information/test-execution/quick-execution" target="_blank">quick execution run</a> will be displayed in the test pane - the successfully executed steps are marked with a green circle and the failed steps are marked with a red circle in front of it.

<table id=no-table>
<colgroup>
        <col width="30%" />
        <col width="30%" />
    </colgroup>
	<tbody>
	<tr>
		<td style="text-align:center; height:10px;">![passed step icon][2]</td>
		<td style="text-align:center; height:10px;">![step failure icon][3]</td>
	</tr>
	<tr>
		<td style="text-align:center;">__Step Passed__</td>
		<td style="text-align:center;">__Step Failed__</td>
	</tr>
	</tbody>
<table>

Each failed step provides additional details for the failure, if you hover over the red circle in front of it. By clicking on that red crossed circle, you open the <a href="/general-information/test-results/step-failure-details" target="_blank">**Step Failure Details**</a> dialog. You can see detailed message for the failure, screenshots for the expected image and image at the time of failure, the DOM tree at the time of failure and suggestion how to solve the error.

![Step Failure Details Dialog][4]

## Visual Debugger

The <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-visual-debugger" target="_blank">Visual debugger</a> has different options for debugging a test during a quick test run. It is often used when the test does not behave as expected, and especially when it is not clear at which action the issue occurs.

The default quick run will trigger the Visual Debugger in the lower right corner of your display. It indicates the current step, includes play and pause ability, and shows additional Debug Options if you set the Debugger options to pause on errors.

![Visual Debugger Indicator][5]

Click **Debugging Options** icon in the Test ribbon to turn the debugger on/off and customize the Auto-Pause Options, if errors occur during the quick execution.

![Test Studio][6]

You can also set a <a href="/features/test-maintenance/steps-pane" target="_blank">Breakpoint to any step</a> where you need to pause the test execution and use the Debugger.

## Partial Test Execution

A useful approach to examine a failing test is to execute it partially to a step (or few steps) before the failing one. Test Studio allows you to <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">execute a test partially with the ***Run...*** options from the Step Context Menu</a>.

![Partial test run][7]

- **To Here** - launches a new instance of the selected browser, execute the preceding (including the selected) test step(s), and finishes the run with recorder attached to the browser.
- **From Here** - execute the subsequent steps in an existing browser instance (must have recording toolbar attached to browser).
- **Selected Steps** - execute the selected step(s) in an existing browser instance (must have recording toolbar attached to browser).

## Annotated Test Run

There are occasions when a test is reported passed, but the actions, which it is expected to perform do not actually happen. In such cases it can be helpful to <a href="/automated-tests/test-execution/quick-run-annotations" target="_blank">enable the annotations</a> during the quick test run. Click the **Toggle Annotation** button to have the browser annotate each step with a brief message and by highlighting that step's target element.

![Toggle Annotation][8]

This will also slow down the test run by the configured amount (in milliseconds) between each step. You can set it either from the menu or by entering a custom value.

> __Tip__
><br>
><br>
> Check <a href="/automated-tests/troubleshooting/use-annotated-run" target="_blank">here how you can use the annotations</a> for troubleshooting a failing test.

## Application Log

The <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log" target="_blank">application log</a> is a list of messages logged by Test Studio throughout the tool usage and bring information for the performed actions in Test Studio. It is usually used, if there are unexpected errors, crashes, or a recommended configuration in the project, which cannot be successfully accomplished.

## Analyze Test List Results

The *Results* tab displays results for all locally and remotely executed test lists. There you can <a href="/general-information/test-results/analyze-test-list-results" target="_blank">analyze the executions</a>, drill down to the individual test step and go back up to the main test list level for each execution.

<div><a href="/getting-started/first-execution">Back to <strong>Execute Your First Test</strong></a><a style="float:right" href="/getting-started/next-steps">Go to <strong>Next Steps</strong></a></div>

[1]: /img/getting-started/first-project/fig14.png
[2]: /img/getting-started/analyze-the-results/fig01.png
[3]: /img/getting-started/analyze-the-results/fig02.png
[4]: /img/getting-started/analyze-the-results/fig03.png
[5]: /img/getting-started/first-project/fig11.png
[6]: /img/getting-started/first-project/fig12.png
[7]: /img/getting-started/analyze-the-results/fig04.png
[8]: /img/getting-started/first-project/fig13.png