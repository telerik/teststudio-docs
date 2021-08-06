---
title: Explore Quick Run Results
page_title: Explore Quick Run Results
description: "Test Studio Quick Run Results. Analyze the results from test run. Failing Test Studio test. Unable to find element. Warning in the execution log. Test Studio Execution log."
position: 0
---
# Explore the Results from Quick Test Execution

The __Quick Run__ results are generated after a <a href="/automated-tests/test-execution/quick-execution#execution-timeouts" target="_blank">Quick Test Execution</a>. These results are stored temporarily and get deleted when you trigger a new Quick Test or reload a project. Use the results while designing the automated tests and when troubleshooting failures.

## Generate the Quick Execution Log

To generate the quick execution log, <a href="/getting-started/first-project#test-recording" target="_blank">Record and execute a test</a>. The generated Quick Run results are displayed in the upper ribbon of the <a href="/features/test-maintenance/steps-pane" target="_blank">Steps Pane</a>. You can see the overall result (**Pass** or **Fail**), open the execution log, or directly clear the results.

![Quick Run results][1]

For each successfully passed action step, you can see images of the page state at the time of the test recording and execution. When troubleshooting a failing test, examine these screenshots to identify if an action is reported as successful, but it wasn't performed as expected.

![Images for passed steps][1a]

## Open and Review the Execution Log

Click the **View Log** button to open and review the quick run execution log. It opens in a new window and provides additional details for the current run:

- Executed test.
- Executing browser.
- Description of the executed steps.
- Reference for the data source, if the <a href="/automated-tests/data-drive-test/what-is-ddt" target="_blank">test is data driven</a>.
- List of warnings about the test configuration, if there are any.
- Full trace of the exceptions, if the test fails.

These details make the execution log a beneficial source of specific information about the test execution and it is often used to debug errors in the tests.

![View Quick Run result][2]

## Successful Test Run with Warnings

The <a href="/automated-tests/elements/elements-find-expression#elements-image" target="_blank">automatic fallback to image-based search of elements</a> logs a warning in the execution log when triggered. The test result is marked as successful as all elements are located and all actions are performed, but if Test Studio fails to locate any element by its primary find expression, this is logged as a message in the execution.

![Successful Test Run with Warnings][3]

> __Tip__
> <br>
> <br>
> A similar warning is logged if the primary element identification is set to <a href="/features/project-settings/find-logic" target="_blank">__Search By Image First__</a>, but the element is found using the recorded find expression instead.

The warning is also listed in the __Steps Result Details__ section and the step is marked with an exclamation mark icon.

![Successful Test Run with Warnings][3a]

## Failed Test Run

A failed test run generates an execution log with additional details about the specific failure.

![Failed Test Run][4]

The __Step Failure Details__ section shows a summarized message for the reason of failure and specific suggestions how to troubleshoot the error.

![Failed Test Run][4a]

> __Tip__
> <br>
> <br>
> Complete details and resolution suggestions are also listed in the <a href="/automated-tests/test-results/step-failure-details" target="_blank">__Step Failure Details__ window</a>.

Any element, which cannot be located by its primary or backup search definition, fails the test and the overall status is reported as failed. The __Step Failure Details__ section shows a summarized message for the failure reason and specific suggestions on how to troubleshoot the error.

![Image based search failure][5a]

The execution log provides additional details for the failure and notes, if the backup search was used.

![Image based search failure][5]

## Collect the Generated Quick Run Result

To share the quick run results with a colleague of yours or in a support ticket, copy the overall execution log by using the __Copy To Clipboard__ button, which is available when the log is opened. Paste and save the data in a text document, which you can zip.

[1]: /img/automated-tests/test-results/new-quick-run-results/fig1.png
[1a]: /img/automated-tests/test-results/new-quick-run-results/fig1a.png
[2]: /img/automated-tests/test-results/new-quick-run-results/fig2.png
[3]: /img/automated-tests/test-results/new-quick-run-results/fig3.png
[3a]: /img/automated-tests/test-results/new-quick-run-results/fig3a.png
[4]: /img/automated-tests/test-results/new-quick-run-results/fig4.png
[4a]: /img/automated-tests/test-results/new-quick-run-results/fig4a.png
[5]: /img/automated-tests/test-results/new-quick-run-results/fig5.png
[5a]: /img/automated-tests/test-results/new-quick-run-results/fig5a.png