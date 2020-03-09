---
title: Export Load Test Results
page_title: Export Load Test Results
description: "Export Load Test Results in Test Studio"
position: 1
---
# Export Load Testing Results

Test Studio allows you to export the generated load test results to either HTML file or an Excel spreadsheet.

## Select a Test Run Result to Export

Under the <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">**Analyze**</a> view in the load test pane are listed all executed test runs. Each of these can be exported using the respective button on the Overall results view. Each of the test run results can be exported one by one.

![Export button][1]

In the download dialog to appear, you can browse the location to store the exported results file, change the name of the file - by default Test Studio uses the <a href="/features/testing-types/load-testing/running-load-test/running-tests#test-run-description" target="_blank">**Test Run Description**</a> for the selected run.

## Results Export in Html

The Html exported file presents the <a href="/features/testing-types/load-testing/load-testing-results/analyzing-results#overall-results-of-the-load-test-run" target="_blank">Overall results graphics and details</a> for the load test run.

![html export][2]

## Results Export in Excel

The Excel export file presents details for the *Page Specific Metrics* listed in the **Overall Test Statistics** tab.

![Overall Test Statistics][3]

The **Error details** tab presents details for the Http errors, if any.

![Error Details][4]

The **Error details** tab presents the snapshot raw data collected at each tick time based on the <a href="/features/testing-types/load-testing/running-load-test/running-tests#sampling-rate" target="_blank">sampling rate</a> set for the test run.

![Raw data][5]

[1]: /img/features/testing-types/load-testing/export-results/fig1.png
[2]: /img/features/testing-types/load-testing/export-results/fig2.png
[3]: /img/features/testing-types/load-testing/export-results/fig3.png
[4]: /img/features/testing-types/load-testing/export-results/fig4.png
[5]: /img/features/testing-types/load-testing/export-results/fig5.png