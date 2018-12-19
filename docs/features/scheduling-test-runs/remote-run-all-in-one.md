---
title: Remote Run All In One Configuration
page_title: Remote Run All In One
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# All-In-One Installation

## Remote Execution

Watch a <a href="http://www.telerik.com/automated-testing-tools/support/videos/best-practices/how-to-setup-test-studio-remote-execution.aspx" target="_blank">video tutorial</a> on how to setup remote execution.

1.&nbsp;  <a href="/getting-started/installation/install-procedure" target="_blank">Install the Scheduling Service and Storage Service components</a> in the **Customize Installation dialog** during Test Studio Installation for the machine or machines that will host these services. These are not selected by default in a Standalone installation.

![Installation Dialog][1]

2.&nbsp; Start Test Studio and click **Configure** in the Scheduling section of the ribbon bar.

![Configure][2]

3.&nbsp; In the dialog that appears click **MongoDB tab**. Verify **MongoDB data path** and **mongod.exe path** and hit **Apply**. Confirm the *MongoDB is started* status at lower left.

![MongoDB][11]

4.&nbsp; In the **Storage** tab verify the connection string and hit **Apply**. Verify the Telerik Storage Service is started in the lower left.

![Storage][12]

5.&nbsp; In the Scheduling tab verify the information displayed and click **Apply**. Verify the Scheduling Service is running from lower left. Optionally you can configure Email (SMTP) server. This is in case you would like to receive scheduling result via email.

![Scheduling][13]

6.&nbsp; <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Configure one or more machines as Execution Servers</a>, run the **Start Execution Server** application and connect the Execution Server to your Scheduling Server.

![Test Runner][3]

7.&nbsp; Open the project that contains the <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> you wish to schedule for execution and click **Connect** in the Scheduling section of the ribbon bar. 

![Connect][4]

8.&nbsp; In the **Scheduling Server Settings** dialog, click **Run Remotely**, input the location of your Scheduling Server, then click **Connect**. In All-In-One installation it is your local machine.

![Run Remotely][5]

9.&nbsp; <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. Your local machine is selected as the execution machine by default.

10.&nbsp; <a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test execution time.

<p id=ports></p>
> Important: If the machines in your configuration have active firewalls, ensure that the following incoming ports are unblocked on the appropriate machines:

> - Scheduling Server: 8009
> - Storage Server: 8492
> - Execution Machine(s): 55555, 8030-8039 (and sometimes <a href="/troubleshooting-guide/load-testing-problems-tg/cannot-dispatch-load-test" target="_blank">a range of ports from 8040 upward</a>)

[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[6]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig6.png
[3]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3.png
[4]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[5]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png

[11]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[12]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[13]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png