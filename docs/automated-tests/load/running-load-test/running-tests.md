---
title: Running Load Tests
page_title: Running Load Tests
description: "Run Load Tests in Test Studio. How to execute a load test in Test Studio"
position: 0
---
# Running Load Tests Locally

Below you can read how to trigger a load test run locally. This type of execution is usually used while designing and adjusting the test. The results, which it generates, can be easily used to troubleshoot possible issues, or missing dynamic values adjustments.

## Run Load Test

Once you have modified the recorded traffic, switch to the local test execution view using the **Run** button.

![Run view of load test](/img/features/testing-types/load-testing/running-tests/fig1.png)

Click **Run Locally** button to initiate execution of the load test.

![Run Test](/img/features/testing-types/load-testing/running-tests/fig7.png)

When the test begins, Test Studio will automatically switch to the **Test Details** screen and show you the test progress as it is being executed. See the <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">Analyzing Results</a> page to learn how to use this screen.

## Test Run Options

The options which you can adjust prior to executing the load test, are listed under the **Test Options** section. These will be associated with the current test run and can be changed for each next execution of the test.

![Test Run Options](/img/features/testing-types/load-testing/running-tests/fig1a.png)

### Test Run Description

Add a description that will be saved along with the test results. Enter any meta data you want here. You might want to record something special about the environment being used or the build of the application being tested. This can serve as a reminder when looking at all the full list of accumulated test results.

![Description](/img/features/testing-types/load-testing/running-tests/fig2.png)

### Sampling Rate

Specify how often you want to take snapshots of the load test performance data. Each sample will be stored in the Results database. Specifying a sample rate that is too short for a long test may overly burden your Load Reporter and/or the SQL database with incoming data. Specifying a sample rate that is too long will reduce test result granularity. If the sample rate is equal to or longer than the length of the load test, there will be no results at all.

![Sampling Rate](/img/features/testing-types/load-testing/running-tests/fig3.png)

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
</table>

## Test Run Goals

You can set goals for load test metrics to define success or failure - choose a metric from the list and define the failure condition, add a custom goal, choose to ignore goals for an initial period. To set a goal from the list, check the box next to the metric you want to measure and input the value for the failure condition.

![Goals](/img/features/testing-types/load-testing/running-tests/fig4.png)

You can choose whether to **stop the test if this goal is met**.

![Goal Met](/img/features/testing-types/load-testing/running-tests/fig5.png)

You can choose ***Add custom goal*** and define a new failure or success condition for any metric.

![Custom Goal](/img/features/testing-types/load-testing/running-tests/fig6.png)

## Disabled Run Button

The “Run Locally” button will be disabled if any of the following prerequisites is not met:

- Ensure the local machine is added as Execution Server in <a href="/features/testing-types/load-testing/managing-vu" target="_blank">Manage Virtual Users</a> dialog and has enough virtual users allocated.
- Ensure a valid <a href="/features/testing-types/load-testing/adding-user-profiles" target="_blank">User Profile</a> is captured and there is any workload set for that profile.
- The <a href="/features/testing-types/load-testing/test-settings#available-users" target="_blank">virtual users set when designing a test</a> should not exceed the users allocated to the local Execution Server.

