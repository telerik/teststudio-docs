---
title: Explore Quick Run Results
page_title: Explore Quick Run Results
description: "Test Studio Quick Run Results. Analyze the results from test run. Failing Test Studio test. Unable to find element. Warning in the execution log. Test Studio Execution log."
position: 0
---
# Explore the Results from Quick Test Execution

The __Quick Run__ results are generated after a <a href="/automated-tests/test-execution/quick-execution#execution-timeouts" target="_blank">Quick test execution</a>. This __result is a temporary stored result__ and its usage is recommended while designing the automated tests and when troubleshooting failures. The current Quick Run result is deleted when a new Quick execution is triggered or project is reloaded.

## Generate the Quick Execution Log

<a href="/getting-started/first-project#test-recording" target="_blank">Record and execute a test</a>. The status of the generated Quick Run result is displayed in the upper ribbon in the <a href="/features/test-maintenance/steps-pane" target="_blank">Steps Pane</a>. You can see the overall result - passed in green or failed in red. You can access the execution log for this quick run through the __View Log__ button, or use the __Clear result__ option to delete the result from this execution.

![Quick Run results][1]

For each __action step, which was successfully passed__, you can see __images of the page state__ at the time of recording the test, and the time of execution. when troubleshooting a failing test, these screenshots are very useful to identify, if an action is reported successful, but it turns out during the test run it wasn't actually performed as expected.

![Images for passed steps][1a]

## Open and Review the Execution Log

Click the **View Log** button to open and review the quick run execution log. It is opened in a separate window and provides additional details for the current run:

- which is the executed test,
- which is the executing browser,
- description of the executed steps,
- if the <a href="/automated-tests/data-drive-test/what-is-ddt" target="_blank">test is data driven</a>, there is reference for the data source,
- if there are any warnings about the test configuration, these are listed,
- full trace of the exceptions in case of failure.

All these details make the execution log a beneficial source of specific information about a test execution and it is often used to debug errors in the tests.

![View Quick Run result][2]

## Successful Test Run with Warnings

The <a href="/automated-tests/elements/elements-find-expression#elements-image" target="_blank">automatic fall back to image based search of elements</a> loga a warning in the execution log when triggered. The test result is marked as successful as all elements are located and all actions are performed, but if Test Studio fails to locate any element by its primary find expression, this is logged as message in the execution for your convenience.

![Successful Test Run with Warnings][3]

> __Tip__
> <br>
> <br>
> Similar warning is logged, if the primary element identification is set to <a href="/features/project-settings/find-logic" target="_blank">__Search By Image First__</a>, but the element is found using the recorded find expression instead.

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

Any __element, which failed to be located by its primary or backup search definition, fails the test__ and the overall status is reported failed. The __Step Failure Details__ section shows a summarized message for the reason of failure and specific suggestions how to troubleshoot the error.

![Image based search failure][5a]

The execution log provides additional details for the failure and notes, if the backup search was used.

![Image based search failure][5]

## Collect the Generated Quick Run Result

If you need to provide the quick run results to a colleague of yours or within a support ticket, you can copy the overall execution log using the __Copy To Clipboard__ button, which is available when the log is opened. Paste and save the data in a text document, which can be distributed zipped.

[1]: /img/automated-tests/test-results/new-quick-run-results/fig1.png
[1a]: /img/automated-tests/test-results/new-quick-run-results/fig1a.png
[2]: /img/automated-tests/test-results/new-quick-run-results/fig2.png
[3]: /img/automated-tests/test-results/new-quick-run-results/fig3.png
[3a]: /img/automated-tests/test-results/new-quick-run-results/fig3a.png
[4]: /img/automated-tests/test-results/new-quick-run-results/fig4.png
[4a]: /img/automated-tests/test-results/new-quick-run-results/fig4a.png
[5]: /img/automated-tests/test-results/new-quick-run-results/fig5.png
[5a]: /img/automated-tests/test-results/new-quick-run-results/fig5a.png