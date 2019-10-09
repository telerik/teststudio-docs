---
title: Monitor Performance Metrics
page_title: Monitor Performance Metrics
description: "Monitor Performance Metrics in Test Studio load test. monitor performance counters of one or more machines during a Test Studio load test run"
position: 1
---
# Monitor Performance Metrics

You can add different performance counters for each machine to be monitored during a load test run. 

> __Note!__ The target machine, which will be monitored, must have either <a href="/general-information/test-studio-run-time" target="_blank">**Run Time edition**</a> or Test Studio installed on it. The <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution server or Test Runner</a> needs to be running so that Test Studio can connect to it for performance monitoring.

In the ___Monitor Performance___ section in the ___Design___ view, click the ___Add Computer___ button to select performance counters for monitoring on one or more machines during your load test

![Add computer][1]

1.&nbsp; Enter the machine name or IP address for the computer you need to monitor. This machine does not need to play a specific role in your load test, but it does need an installation of __Test Studio Runtime Edition__ or higher. Click the **Test Connection** button to ensure Test Studio can communicate with the target machine.

![Computer name][2]

2.&nbsp; Once the connection to the target machine is verified, the list with all **Available Counters** is populated.

![Available Counters][3]

3.&nbsp; Select each object you wish to monitor. Then, you may select specific counters for each object in the sub-list.

![Specific counters][4]

5.&nbsp; To save this set of performance counters for use with other load tests or machines:

  a. Click ![disk][5]

  b. Input a name for the performance template. 

![Template][6]

6.&nbsp; Click **Save**.

![Save][7]

 An entry for this machine will appear under **Monitor Performance**. Click the checkbox next to the machine name to toggle performance monitoring for this machine. 

![Entry][8]

[1]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig1.png
[2]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig2.png
[3]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig3.png
[4]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig4.png
[5]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig5.png
[6]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig6.png
[7]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig7.png
[8]: /img/features/testing-types/load-testing/monitor-perf-metrics/fig8.png