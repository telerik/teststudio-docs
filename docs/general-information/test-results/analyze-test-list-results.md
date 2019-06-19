---
title: Analyze Test List Results
page_title: Analyze Test List Results
description: "Test Studio Test List Results. Analyze test list results. Explore test list results in Test Studio."
previous_url: /user-guide/test-results/analyze-test-results.aspx, /user-guide/test-results/analyze-test-results, /getting-started/test-results/analyze-test-results
position: 1
---
# Analyze Test List Results

The **Test Results** panel allows you to traverse test execution results, drilling down to the individual test step and back up again to the test list level.

1.&nbsp; To see the results for a test list, double-click the result in the calendar.

2.&nbsp; The **Test Results** panel appears on the right. The test results panel shows results for the entire test list.

3.&nbsp; The **Passed/Total** column shows that all steps of both tests passed. Double-clicking a test in this list drills down to show the steps of that test.

![Test results][1]

4.&nbsp; Double-click a test in the **Test Results** view to see the result of each test step. The bread crumb trail at the top of the panel now shows the test list followed by the test name.

![Step results][2]

5.&nbsp; Click the top level in the bread crumb trail to jump directly back to the test list result.

## Test as Step Results

If the test contains a <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a>, ![More icon][3] appears next to the Test as Step. Double click that step to view the step results for that Test as Step.

![Step as step results][4]

## Element Not Found Results

### Successful Test List Run with Warnings

The automatic fall back to image based search of elements will log a warning in the test list result. The test list result is marked as successful as all elements are located, but if any element failed to be located by its default find expression, it will be listed for your convenience.

![Successful Test List Result with Warnings][10]

Double click the result to see details for the warning in the test list result.

![Test List result Warning details][11]

### Resolve the Warning

Test Studio provides direct access from the test list results to the <a href="/features/elements-explorer/find-element" target="_blank">Element Edit Pane</a> in order to modify the element's find expression.

![Resolve Find Expression warning][12]

### Failed Test List Run

An element, which failed to be located by its backup image search, will fail the test and test list result will be reported as Failed. The test result provides details for the failure in the <a href="/general-information/test-results/step-failure-details" target="_blank">step failure details</a>, including if the image based search was used.

![Image based search failure in step failure details][13]

## In Development Tests Results

If the test list setting **ExecuteTestsInDevelopment** is set to false, the tests flagged <a href="/features/test-maintenance/tests-in-development" target="_blank">'In Development'</a> will be skipped in the execution. Opening the results details will inform you that the test is in development.

![In development tests results][5]

## Automatic Re-run of Failed Tests Results

If the test list setting **RerunFailedTests** is enabled, the <a href="/getting-started/test-execution/test-list-execution#automatic-re-run-of-failed-tests" target="_blank">failed tests</a> in a test list run will be automatically executed after the test list finishes. The results of the second test execution will be displayed in the detailed result list under the initial test execution results, but will be marked with an exclamation mark and flagged as 'Rerun'.

![Automatic Re-run of Failed Tests Results][6]

## Test List Screen Recording Results

If the test list settings to <a href="/getting-started/test-execution/test-list-execution#recording-of-test-list-execution" target="_blank">capture the screen</a> during test list execution are enabled and a video is available, a _'Screen Recording Info'_ icon is displayed in the detailed test list results for the tests which triggered video recording.

![Screen Recording Info icon][7]

Click the _'Screen Recording Info'_ icon for any of the tests which triggered video recording, and choose to play the video directly or copy to clipboard the output folder and navigate to files directly in the File Explorer.

![Play the recorded video][8]

[1]: /img/general-information/test-results/analyze-test-results/fig1.png
[2]: /img/general-information/test-results/analyze-test-results/fig2.png
[3]: /img/general-information/test-results/analyze-test-results/fig3.png
[4]: /img/general-information/test-results/analyze-test-results/fig4.png
[5]: /img/general-information/test-results/analyze-test-results/fig5.png
[6]: /img/general-information/test-results/analyze-test-results/fig6.png
[7]: /img/general-information/test-results/analyze-test-results/fig7.png
[8]: /img/general-information/test-results/analyze-test-results/fig8.png
[10]: /img/general-information/test-results/analyze-test-results/fig10.png
[11]: /img/general-information/test-results/analyze-test-results/fig11.png
[12]: /img/general-information/test-results/analyze-test-results/fig12.gif
[13]: /img/general-information/test-results/analyze-test-results/fig13.png