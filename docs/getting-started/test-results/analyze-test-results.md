---
title: Analyze Test Results
page_title: Analyze Test Results
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-results/analyze-test-results.aspx, /user-guide/test-results/analyze-test-results
position: 1
---
# Analyze Test Results

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

[1]: /img/getting-started/test-results/analyze-test-results/fig1.png
[2]: /img/getting-started/test-results/analyze-test-results/fig2.png
[3]: /img/getting-started/test-results/analyze-test-results/fig3.png
[4]: /img/getting-started/test-results/analyze-test-results/fig4.png
[5]: /img/getting-started/test-results/analyze-test-results/fig5.png
[6]: /img/getting-started/test-results/analyze-test-results/fig6.png
[7]: /img/getting-started/test-results/analyze-test-results/fig7.png
[8]: /img/getting-started/test-results/analyze-test-results/fig8.png