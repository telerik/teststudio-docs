---
title: Analyzing Results
page_title: Analyzing Results
description: "Analyzing Test Studio load testing results. How to understand the load testing results in Test Studio."
position: 0
---
# Analyzing Results

During your test runs you’ll be shown clear, informative screens letting you know the state of your system throughout the run. You’re able to focus in on exactly the metrics you’re interested in, such as total errors, traffic size, time to first byte, and other common metrics.

## Monitor Load Test Results During the Test Run

Once a load test run is started, the **Run** load test pane is switched to the **Analyze** view and allows you to monitor the collected metrics live during the test execution. The first data to appear is from the first sampling rate interval. Then, these get updated on each next sampling rate tick time.

![Results showed during the test run][1a]

The current running test results appear at the top of the list with all previous runs of the same load test. This screen shows the aggregated data collected from all of the load agents, including the case when running a load test on multiple machines.

![Current test run Results][1]

In the case when using <a href="/features/testing-types/load-testing/running-load-test/running-tests#test-run-goals" target="_blank">test run goals</a> to determine whether a test is failed or passed, the run result will be marked with a red or green vertical bar to the left.

![Passed or Failed test indication for running tests with predefined goals][2]

## Overall Results of the Load Test Run

The **Overall Results** can be accessed through the *'Magnifier'* icon for each load test run and are also automatically displayed and updated live during the test run. Here you can export the results, or delete the current load test run results. 

![Overall Results][3]

These are separated in three tabs - Dashboard, Goals and Page Specific Metrics, to help you easier sort the necessary details.

### Dashboard Results

The **Dashboard** tab displays graphs of the progress for few of the gathered metrics during the test run and the peak value for these, based on the entire test run for finished execution, or based on the so far collected sampling for a running test. These are *Peak Average Response Time*, *Peak Current Virtual Users*, *Peak HTTP Errors/second*, *Peak Responses Received/second*.

![Dashboard Results][4]

### Goals Results

The **Goal** tab is empty for load test runs without set goals.

![Empty Goals Results][5]

When the load test is using goals to determine its outcome, the **Goals** tab shows details for the particular goal.

![Goals Results][6]

### Page Specific Metrics Results

The **Page Specific Metrics** tab provides details for each separate URL in the load user profile - what its average response time is and if it generated any HTTP errors.

![Page Specific Metrics Results][7]

A click on any of the listed URLs, opens additional details for the HTTP response code and status message.

![Page Specific Metrics http response details][8]

## Analyze Detailed Metrics from the Load Test Run

Each load test result includes detailed data for further metrics collected during the run. These are grouped under the *'Graph'* icon and you can choose for analysis between the overall test metrics, or per machine specific metrics, for the case of using multiple machines to run the load test.

![Detailed Metrics Results][9]

You can choose up to **six** of the listed metrics and these appear in the _Result_ view as a table with statistical calculations and a graph view for better presentation of the test run results,

![Statistical calculations and graph view][10]

Moving the mouse through the graphical representation of the collected metrics, changes the values in the ***'Current'*** column.

![Current column][11]

The rest of the columns in the statistical table remains the same - these represent ***Median, Max, Min and Scale*** values, which are constant and calculated based on the collected data from the selected run.

![Constant values calculated based on the collected metrics][12]

## Compare Metrics from Load Test Runs

The _Analyze_ screen in the _Result_ view allows you to select metrics for comparison from different load agents and/or test runs.

### Compare Metrics from Different Load Agents

You can check and compare up to **six** of the collected metrics from the different load agents in a single run.

![Compare different load agents][13]

The sample test scenario was executed on a single machine and thus the collected data for Overall test and specific machine is basically the same -thus the graphs are one over the other. Still, the statistical table shows two rows for the different sources.

![Different load agents source][14]

### Compare Metrics from Different Test Runs

You can select up to six metrics to compare in the _Analyze_ screen from different test runs. 

![Select metrics from different runs][15]

The table with statistical values shows the description of each test run and which is the selected load agent to present data for.

![Different load test runs][16]

## Collected Metrics Description

<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
}
table.docs th {
color:#fff;
background-color:#00аб8е;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>
<table class="docs">
<tr>
	<th>Metric</th><th>Description</th>
</tr>
<tr>
	<td>Average Response Time</td><td>Over the life of the test, the average of how long each user response took to be received. Time is measured from when the request was sent to when the end of the response was received.</td>
</tr>
<tr>
	<td>Average Time to First Byte</td><td>Over the life of the test, the average amount of delay between when the HTTP request was sent to when the response was received.</td>
</tr>
<tr>
	<td>Bytes Received per Second</td><td>The total number of bytes received per second across all virtual users. Only information contained in the body of the response is counted. Header information is not counted.</td>
</tr>
<tr>
	<td>Bytes Sent per Second</td><td>The total number of bytes sent per second across all virtual users. Only information contained in the body of the request is counted. Header information is not counted.</td>
</tr>
<tr>
	<td>Completed Virtual Users</td><td>The total count of all virtual users over the life of the test that completed all of their requests without faulting.</td>
</tr>
<tr>
	<td>Created Virtual Users</td><td>The total count of all virtual users over the life of the test that were created.</td>
</tr>
<tr>
	<td>Current Virtual Users</td><td>The number of active virtual users at the time a load measurement was taken.</td>
</tr>
<tr>
	<td>Faulted Virtual Users</td><td>The total count of all virtual users over the life of the test that had a fault, such as an internal exception.</td>
</tr>
<tr>
	<td>HTTP Errors Per Second</td><td>The number of HTTP errors received across all virtual users per second. The load test agent counts HTTP status codes between 400 and 599 as errors and any general unhandled exception while making the HTTP request to the web server, e.g. the HTTP connection was closed, as an error.</td>
</tr>
<tr>
	<td>HTTP Errors Per Second</td><td>The number of HTTP errors received across all virtual users per second. The load test agent counts HTTP status codes between 400 and 599 as errors and any general unhandled exception while making the HTTP request to the web server, e.g. the HTTP connection was closed, as an error.</td>
</tr>
<tr>
	<td>Requests Sent per Second</td><td>The number of HTTP requests sent per second across all virtual users.</td>
</tr>
<tr>
	<td>Responses Received per Second</td><td>The number of HTTP responses received per second across all virtual users. </td>
</tr>
<table>

[1a]: /img/features/testing-types/load-testing/analyzing-results/fig1a.png
[1]: /img/features/testing-types/load-testing/analyzing-results/fig1.png
[2]: /img/features/testing-types/load-testing/analyzing-results/fig2.png
[3]: /img/features/testing-types/load-testing/analyzing-results/fig3.png
[4]: /img/features/testing-types/load-testing/analyzing-results/fig4.png
[5]: /img/features/testing-types/load-testing/analyzing-results/fig5.png
[6]: /img/features/testing-types/load-testing/analyzing-results/fig6.png
[7]: /img/features/testing-types/load-testing/analyzing-results/fig7.png
[8]: /img/features/testing-types/load-testing/analyzing-results/fig8.png
[9]: /img/features/testing-types/load-testing/analyzing-results/fig9.png
[10]: /img/features/testing-types/load-testing/analyzing-results/fig10.png
[11]: /img/features/testing-types/load-testing/analyzing-results/fig11.png
[12]: /img/features/testing-types/load-testing/analyzing-results/fig12.png
[13]: /img/features/testing-types/load-testing/analyzing-results/fig13.png
[14]: /img/features/testing-types/load-testing/analyzing-results/fig14.png
[15]: /img/features/testing-types/load-testing/analyzing-results/fig15.gif
[16]: /img/features/testing-types/load-testing/analyzing-results/fig16.png
