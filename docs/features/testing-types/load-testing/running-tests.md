---
title: Running Tests
page_title: Running Tests
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/load-testing/load-running-tests.aspx
position: 17
---
# Running Tests

This document describes how to run a load test immediately from the Test tab. As of 2013 R1, you can also <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">add load tests to a test list</a> and schedule them for remote execution.

When you have finished designing your load test and are ready to begin a load test run, click the **Run** button in the **Steps** ribbon. 

![Run][1]

Prior to executing the load test there are two parameters you can adjust:

- **Test Run Description** - Add a description that will be saved along with the test results. Enter any meta data you want here. You might want to record something special about the environment being used or the build of the application being tested. This can serve as a reminder when looking at all the full list of accumulated test results.

![Description][2]

- **Sampling Rate** - Specify how often you want to take snapshots of the load test performance data. Each sample will be stored in the Results database. Specifying a sample rate that is too short for a long test may overly burden your Load Reporter and/or the SQL database with incoming data. Specifying a sample rate that is too long will reduce test result granularity. If the sample rate is equal to or longer than the length of the load test, there will be no results at all.

![Sampling Rate][3]

Choose an appropriate value for the Sampling Rate property for the load test run based on the duration of your load test. A smaller sample rate, such as the default value of 5 seconds, requires more space in the load test results database. For longer load tests, increasing the sample rate reduces the amount of data that you collect.

Here are some guidelines for sample rates: 

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
	<th>Load Test Duration</th><th>Recommended Sample Rate</th>
</tr>
<tr>
	<td>< 1 Hour</td><td>5 seconds </td>
</tr>
<tr>
	<td>1 - 3 Hours</td><td>15 seconds</td>
</tr>
<tr>
	<td>3 - 6 Hours</td><td>30 seconds</td>
</tr>
<tr>
	<td>6-12 Hours</td><td>1 minute</td>
</tr>
<tr>
	<td>12-60 hours</td><td>5 minutes</td>
</tr>
<tr>
	<td>> 60 hours</td><td>10 minutes</td>
</tr>
<table>

- **Goals** – Set goals for load test metrics to define success or failure. You can choose a metric from the list and define the failure condition, add a custom goal, and choose to ignore goals for an initial period. To set a goal from the list, check the box next to the metric you want to measure and input the value for the failure condition.

![Goals][4]

 You can choose to stop the test if this goal is met.

![Goal Met][5]

You can choose ‘Add custom goal’ and define a new failure or success condition for any metric.

![Custom Goal][6]

Click **Run this test** to initiate execution of the load test. 

![Run Test][7]

When the test begins, Test Studio will automatically switch to the **Test Details** screen and show you the test as it is being executed. See the <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">Analyzing Results</a> page to learn how to use this screen.

## Disabled Run Button

The “Run Locally” button will be disabled if any of the following prerequisites is not met:

- Ensure the local machine is added as Execution Server in <a href="/features/testing-types/load-testing/managing-vu" target="_blank">Manage Virtual Users</a> dialog and has enough virtual users allocated.
- Ensure a valid <a href="/features/testing-types/load-testing/adding-user-profiles" target="_blank">User Profile</a> is captured and there is any workload set for that profile.
- The <a href="/features/testing-types/load-testing/test-settings#available-users" target="_blank">virtual users set when designing a test</a> should not exceed the users allocated to the local Execution Server.

[1]: /img/features/testing-types/load-testing/running-tests/fig1.png
[2]: /img/features/testing-types/load-testing/running-tests/fig2.png
[3]: /img/features/testing-types/load-testing/running-tests/fig3.png
[4]: /img/features/testing-types/load-testing/running-tests/fig4.png
[5]: /img/features/testing-types/load-testing/running-tests/fig5.png
[6]: /img/features/testing-types/load-testing/running-tests/fig6.png
[7]: /img/features/testing-types/load-testing/running-tests/fig7.png
[8]: /img/features/testing-types/load-testing/running-tests/fig8.png



