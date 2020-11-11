---
title: Scheduling Results
page_title: Scheduling Results
description: "Test Studio results from scheduled test runs. Scheduling Results. Scheduling calendar. "
position: 9
---
# Scheduling Results

Now that there is a configured Scheduling setup and a test list is executed <a href="/features/scheduling-test-runs/run-list-remotely" target="_blank">remotely</a>, or <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">scheduled</a>, the generated results will be displayed in the <a href="/general-information/test-results/calendar" target="_blank">Results tab</a> in Test Studio.

## Reload From Server

After the scheduled test list runs on the Execution server(s), the results will be automatically populated in the Calendar. Alternatively, you can update the results view with the help of the **Reload** button.

1.&nbsp; On the **Results** tab, click the **Reload** button in the **Scheduling Server** ribbon.

![Reload][1]

2.&nbsp; The pending run should change from yellow to either green or red, indicating whether the test list passed or failed.

![Timeline][2]

3.&nbsp; Double click the result to drill down into the test list. You'll see a summary of each test's result in the test list.

![Test Results][3]

4.&nbsp; Go further by double clicking each test. For more information see the <a href="/getting-started/test-results/analyze-test-results" target="_blank">Analyze Test Results</a> page.

![Test Steps][4]

## Publish To Server

Use this button to publish the currently selected locally executed test list result to the Scheduling server. Those results will also appear in the <a href="/general-information/test-results/executive-dashboard" target="_blank">Executive Dashboard</a>.

![Publish to Server][5]

## Manage Results

Click **Manage Results** to view and/or delete test list results on the Scheduling server.

![Manage Results][6]

To delete one or more test results, click the check box next to the results and click ![Delete Results Button][8].

![Delete Results][7]

## Executive Dashboard

With Test Studio version 2019 R3 and later you can <a href="/general-information/test-results/executive-dashboard" target="_blank">setup the Execution Dashboard</a>. It allows you to view remote test list results from the browser on any device that can access it.

[1]: /img/features/scheduling-test-runs/scheduling-results/fig1.png
[2]: /img/features/scheduling-test-runs/scheduling-results/fig2.png
[3]: /img/features/scheduling-test-runs/scheduling-results/fig3.png
[4]: /img/features/scheduling-test-runs/scheduling-results/fig4.png
[5]: /img/features/scheduling-test-runs/scheduling-results/fig5.png
[6]: /img/features/scheduling-test-runs/scheduling-results/fig6.png
[7]: /img/features/scheduling-test-runs/scheduling-results/fig7.png
[8]: /img/features/scheduling-test-runs/scheduling-results/fig8.png