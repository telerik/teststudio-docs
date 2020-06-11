---
title: Local Scheduled Execution
page_title: Local Scheduled Test List Execution
description: "With Test Studio you can schedule tests and test lists on a single machine. The below article describe the necessary steps to enable scheduling for a Standalone Test Studio installation."
position: 2
---
# Local Scheduled Test List Execution

With Test Studio you can schedule tests and test lists on a single machine. The local scheduling setup keeps the test list results in the local project root folder. The below article describe the necessary steps to enable scheduling for a Standalone Test Studio installation.

## Installing Test Studio for Local Scheduled Runs

1.&nbsp; <a href="/getting-started/installation/install-procedure" target="_blank">Install the default Test Studio configuration</a> (The Telerik Scheduling and Storage services are not selected).

2.&nbsp; Start Test Studio - this will also start the **Test Runner** process, which will appear in your System Tray. This is the process that handles the scheduled test execution in the local setup. If this is not running, no scheduled tests will be started.

![Test Studio Test Runner][1]

## Setting Up a Project for Local Scheduled Runs

1.&nbsp; Open any project that contains the <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> you wish to schedule for execution, or create a new empty project and create a sample test list in it.

2.&nbsp; Under the _Project_ tab click the **Connect** option in the *Scheduling* section of the ribbon.

![Connect][2]

3.&nbsp; Ensure the project is connected to run locally - in the **Scheduling Server Settings** dialog, click **Run Locally**, then **OK**.

![Run Locally][3]

## Schedule a Test List

<a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. Your local machine is selected as the execution machine by default.

## View Results of Local Scheduled Run

<a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test execution time. As this is a local test list run, the result files are physically stored on the local disk under the Results sub-folder in the project root one.

> **Note!** If the used machine has an active firewall, ensure that the following ports are unblocked: 55555, 8009.

[1]: /img/features/scheduling-test-runs/local-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/local-run-all-in-one/fig2.png
[3]: /img/features/scheduling-test-runs/local-run-all-in-one/fig3.png