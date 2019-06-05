---
title: Local Run All In One Configuration
page_title: Local Run All In One 
description: "With Test Studio you can schedule tests and test lists on a single machine. The below article describe the necessary steps to enable scheduling for a Standalone Test Studio installation. "
position: 2
---
# All-In-One Installation

With Test Studio you can schedule tests and test lists on a single machine. The below article describe the necessary steps to enable scheduling for a Standalone Test Studio installation. 

## Local Run

1.&nbsp;  <a href="/getting-started/installation/install-procedure" target="_blank">Install the default configuration</a> (Scheduling and Storage are not selected).

2.&nbsp; Start Test Studio. An icon will appear in your System Tray for the **Test Runner** process. This process handles test scheduling and scheduled test execution. 

![Test Runner][1]

3.&nbsp; Open the project that contains the <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> you wish to schedule for execution.

4.&nbsp; Click **Connect** in the Scheduling section of the ribbon bar.

![Connect][2]

5.&nbsp; In the **Scheduling Server Settings** dialog, click **Run Locally**, then **OK**.

![Run Locally][3]

6.&nbsp; <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. Your local machine is selected as the execution machine by default.

7.&nbsp; <a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test execution time.

> Important: If the All-In-One machine has an active firewall, ensure that the following ports are unblocked: 55555, 8009, and 8030-8039.

[1]: /img/features/scheduling-test-runs/local-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/local-run-all-in-one/fig2.png
[3]: /img/features/scheduling-test-runs/local-run-all-in-one/fig3.png