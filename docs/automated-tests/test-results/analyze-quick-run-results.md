---
title: Explore Quick Run Results
page_title: Explore Quick Run Results
description: "Test Studio Quick Run Results. Analyze the results from test run. Failing Test Studio test. Unable to find element. Warning in the execution log. Test Studio Execution log."
position: 0
---
# Explore the Results from Quick Test Execution

The Quick Run results are generated after a <a href="/automated-tests/test-execution/quick-execution#execution-timeouts" target="_blank">Quick test execution</a>. This result is a temporary stored result and its usage is recommended while designing the automated tests and when troubleshooting failures. The current Quick Run result is deleted when a new Quick execution is triggered or project is reloaded.

## Generate the Quick Execution Log

<a href="/getting-started/first-project#test-recording" target="_blank">Record and execute a test</a>. The generated Quick Run results are displayed in the upper ribbon in the <a href="/features/test-maintenance/steps-pane" target="_blank">Steps Pane</a>. You can see the overall result - passed or failed, open the execution log, or directly clear the results.

![Quick Run results][1]

## Open and Review the Execution Log

Click the ***'View Log'*** button to review the quick run log in details. A separate window gets opened with listed details for the current run - executed test, executing browser, steps description, data source details, warnings, exceptions in case of failure.

![View Quick Run result][2]

## Successful Test Run with Warnings

The automatic fall back to image based search of elements will log a warning in the execution log. The test result is marked as successful as all elements are located, but if any element failed to be located by its default find expression, it will be listed for your convenience.

![Successful Test Run with Warnings][3]

## Failed Test Run

A failed test run generates an execution log with additional details what caused the failure. Complete details and resolution suggestions are listed in the <a href="/automated-tests/test-results/step-failure-details" target="_blank">__Step Failure Details__</a>.

![Failed Test Run][4]

An element, which failed to be located by its backup image search, will fail the test and the execution log will be reported as Failed. The result provides details for the failure including if the image based search was used.

![Image based search failure][5]

## Collect the Generated Quick Run Result

If you need to provide the quick run results to a colleague of yours or within a support ticket, you can easily copy the overall result using the ___Copy To Clipboard___ button and paste the data in a text document - you can use Notepad, for example. Save the newly added content and distribute it zipped.

[1]: /img/automated-tests/test-results/analyze-quick-run-results/fig1.png
[2]: /img/automated-tests/test-results/analyze-quick-run-results/fig2.png
[3]: /img/automated-tests/test-results/analyze-quick-run-results/fig3.png
[4]: /img/automated-tests/test-results/analyze-quick-run-results/fig4.png
[5]: /img/automated-tests/test-results/analyze-quick-run-results/fig5.png