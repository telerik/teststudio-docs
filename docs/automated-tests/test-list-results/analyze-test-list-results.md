---
title: Analyze Test List Results
page_title: Analyze Test List Results
description: "Test Studio Test List Results. Analyze test list results. Explore test list results in Test Studio. Scheduling failure."
previous_url: /user-guide/test-list-results/analyze-test-results.aspx, /user-guide/test-list-results/analyze-test-results, /getting-started/test-list-results/analyze-test-results
position: 1
---
# Analyze Test List Results

The __Results__ tab in Test Studio provides provides an overall view of all test list runs. Along with that you can explore each separate test list result in details, check if there are rerun tests, or elements found by their image as fallback from the set find expression, resolve any failures and many others. 

This article will guide you through the possible messages you can see in test list results and how to act upon these.

## Open Test List Result

Choose a result to explore in details and double click it to see the __Test Results__ panel on the right side of the calendar.

![Open Test list result][0]

The **Test Results** panel shows results for the entire test list, the machine on which it was executed, the overall result of each individual test in the test list.

![Test results][1]

By selecting a test from the test list, you can see and copy __the execution log for the test run__ (1) or switch to its steps in the __Test__ (2) ribbon.

![Test results][1a]

The **Test Results** panel allows you to traverse test execution results, drilling down to the individual tests' steps and back up again to the test list level. __Double-click a test from the list__ to see the result of each step in it. The _breadcrumb trail_ at the top of the panel shows the test list followed by the test name. Click the top level in the _breadcrumb trail_ to jump directly back to the test list result.

![Step results][2]

## Failed Test List Result

If one test in the test list fails, the overall status of the test list is reported as _Failed_. To find out details about what caused the failure, you can drill down to the failing test and step. The faulty step will be marked with red cross sign to indicate that it wasn't successfully executed. __Double click the red cross and open the <a href="/automated-tests/test-results/step-failure-details" target="_blank">step failure details</a>__, which provide useful information for the failure.

![Step results][2a]

## Performance Test List Results

When you drill down the results of a <a href="/getting-started/test-execution/test-lists-type-standalone" target="_blank">Performance Test List</a> execution, there is an additional icon listed in the **Test Results** panel - this is the **Stopwatch**.

![Stopwatch icon][30]

When you click the **Stopwatch** icon the step results switch to show the overview details for the performance run - _Total Time_, _Client_ and _Server Time_, _Size_ (of transferred data) and _Http Errors_. These are the details, which can be explored in the <a href="/automated-tests/performance/overview-button" target="_blank">Overview view</a> in the __Performance tab__.

![Performance test list results][31]

> __Tip__
><br>
><br>
> If you need to review the performance test runs in further depth and compare these with previous runs, ensure that the performance results are stored in the same folder for each run - this is the folder, which you specify when <a href="/automated-tests/performance/gather-perfomance-data" target="_blank">setting up the performance run</a>. Then the performance data will be available in the __Perfrmance__ tab for the respective test in project.

## Test as Step Results in a Test List

If a test contains another <a href="/features/custom-steps/test-as-step" target="_blank">test executed as step</a>, the column _More_ indicates that there are more details to drill down. __Double click the test as step__ to view the detailed results for this test as step. The _breadcrumb trail_ at the top of the panel now shows the test list followed by the main test name and then the name of the test as step. Clicking on any of the tests in the _breadcrumb trail_ will get you back to the selected level.

![Test as step results][4]

## Element Not Found Results

One of the common scenarios in a troublesome test run is related to the elements used in the Test Studio tests and that these cannot be located on current window in the application under test. Test Studio provides different options to identify elements during run-time - you can use a find expression, or an image. Whichever is set, the other will be used as a fall back search option for the test run to find the element in the active application. Based on this specific mechanism for Test Studio, there are few different results you can see in regards the element identification apart from a successful test list run.

### Successful Test List Run with Warnings

The automatic fall back to image based search of elements will log a warning in the test list result if it was used. The test list result is marked as successful as all elements are located, but if any element failed to be located by its default find expression, it will be listed for your convenience.

![Successful Test List Result with Warnings][10]

> __Tip__
><br>
><br>
> If the project is set to first use images to locate the elements, the warnings will appear, if the image was not found and the element was located using its find expression.

Double click the result to see details for the warning in the test list result.

![Test List result Warning details][11]

### Resolve the Warning

Test Studio provides direct access through the button in the _More_ column to open the <a href="/features/elements-explorer/find-element" target="_blank">Element Edit Pane</a> and modify the element's find expression.

![Resolve Find Expression warning][12]

### Failed Test List Run

An element, which failed to be located by its backup search, will fail the test and the overall test list result will be reported as _Failed_. The particular test's result provides details for the failure in the <a href="/automated-tests/test-results/step-failure-details" target="_blank">step failure details</a>, including if the backup search was used.

![Image based search failure in step failure details][13]

## In Development Tests Results

If the test list setting **ExecuteTestsInDevelopment** is set to false, the tests flagged <a href="/features/test-maintenance/tests-in-development" target="_blank">'In Development'</a> will be skipped in the test list execution. Opening the results details will inform you that the test is in development and it wasn't executed.

![In development tests results][5]

## Automatic Re-run of Failed Tests Results

If the test list setting **RerunFailedTests** is enabled, the <a href="/getting-started/test-execution/test-list-execution#automatic-re-run-of-failed-tests" target="_blank">failed tests in a test list run will be automatically executed</a> after the rest of the tests are finished. The results of the rerun test execution will be displayed in the overall list result and placed under the same test's first execution results, but will be marked with an exclamation mark and flagged as 'Rerun'.

![Automatic Re-run of Failed Tests Results][6]

## Test List Screen Recording Results

If the test list settings to <a href="/getting-started/test-execution/test-list-execution#recording-of-test-list-execution" target="_blank">capture the screen during test list execution</a> are enabled and a video is available, a _'Screen Recording Info'_ icon is displayed in the overall test list results for the tests which triggered video recording.

![Screen Recording Info icon][7]

Click the _'Screen Recording Info'_ icon for any of the tests which triggered video recording, and choose to play the video directly or copy to clipboard the output folder and navigate to files directly in the File Explorer.

![Play the recorded video][8]

[0]: /img/automated-tests/test-list-results/calendar/fig6.png
[1]: /img/automated-tests/test-list-results/analyze-test-results/fig1.png
[1a]: /img/automated-tests/test-list-results/analyze-test-results/fig1a.png
[2]: /img/automated-tests/test-list-results/analyze-test-results/fig2.png
[2a]: /img/automated-tests/test-list-results/analyze-test-results/fig2a.png
[3]: /img/automated-tests/test-list-results/analyze-test-results/fig3.png
[4]: /img/automated-tests/test-list-results/analyze-test-results/fig4.png
[5]: /img/automated-tests/test-list-results/analyze-test-results/fig5.png
[6]: /img/automated-tests/test-list-results/analyze-test-results/fig6.png
[7]: /img/automated-tests/test-list-results/analyze-test-results/fig7.png
[8]: /img/automated-tests/test-list-results/analyze-test-results/fig8.png
[10]: /img/automated-tests/test-list-results/analyze-test-results/fig10.png
[11]: /img/automated-tests/test-list-results/analyze-test-results/fig11.png
[12]: /img/automated-tests/test-list-results/analyze-test-results/fig12.gif
[13]: /img/automated-tests/test-list-results/analyze-test-results/fig13.png
[30]: /img/automated-tests/test-list-results/export-test-results/fig3.png
[31]: /img/automated-tests/test-list-results/analyze-test-results/fig31.png
