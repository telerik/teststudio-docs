---
title: Analyzing Results
page_title: Analyzing Results
description: "Analyzing Test Studio load testing results. How to understand the load testing results in Test Studio."
position: 0
---
# Analyzing Results

During your test runs you’ll be shown clear, informative screens letting you know the state of your system throughout the run. You’re able to focus in on exactly the metrics you’re interested in, such as total errors, traffic size, time to first byte, and other common metrics.

This screen shows you the aggregated data collected from all of the load agents stored in the Results Database that are associated with the load controller you are currently connected to.

![Analyze Results][1]

For each result, click ![Details Icon][2] for test details or click ![Analysis Icon][3] to analyze results.

![Icons][4]

 Choose one of the results listed on the left to see the detailed data for that result set. Each result has a colored vertical bar to the left: green indicates success, red failure.

![Details][5]

The details screen shows up-to-date information about the current state of the selected test, separated into the Dashboard, Goals, and Page Specific Metrics.

The Dashboard page displays a graph of the progress of test goals.

![Dashboard][6]

The Goals page displays a summary of which goals passed or failed, and why.

![Goals][7]

The Page Specific Metrics screen displays information for specific pages. This includes the full URL, the total HTTP errors for that URL, and the goal results for that URL.

![Page Specific Metrics][8]

Click a specific URL to see error details.

![URL Details][9]

The analysis screen lets the user compare up to 5 metrics from different runs at the same time.

![Analysis Screen][10]

Choose to analyze data from the Overall Test and/or individual agents:

![Agents][11]

Statistics for each selected metric appear at the top of the analysis screen.
A graph of the selected metrics appears below the statistics.

![Statistics][12]

Drag the vertical bar to view the metric values for a specific time.

![Current][13]

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