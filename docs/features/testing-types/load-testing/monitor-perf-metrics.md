---
title: Monitor Performance Metrics
page_title: Monitor Performance Metrics
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 11
---
# Monitor Performance Metrics

> The target machine to be monitored must have either <a href="/general-information/test-studio-run-time" target="_blank">**Run Time edition**</a> or Test Studio installed on it. The <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">execution server</a> needs to be running before Test Studio can connect to it for performance monitoring.

To monitor performance counters of one or more machines during your load test:

1.&nbsp; In the Test tab for your load test, click ![Add][1]  under Monitor Performance.

2.&nbsp; Enter the machine name or IP address for the computer you wish to monitor. This machine does not need to play a specific role in your load test, but it does need an installation of Test Studio Runtime Edition or higher.

![Computer name][2]

3.&nbsp; Click **Test Connection** to ensure Test Studio can communicate with the target machine.

![Test Connection][3]

4.&nbsp; If Test Studio can connect to the target machine, the **Available Counters** list will populate. Click each object you wish to monitor. Then, you may choose to select specific counters for each object under **Counter**.

![Available counters][4]

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