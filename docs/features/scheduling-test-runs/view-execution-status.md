---
title: View Execution Status
page_title: View Execution Status
description: "Test Studio Execution Status view. View the status of the Test Studio Execution Servers connected to a Test Studio Scheduling Server. Access the execution machines details and logging from the Test Studio Project"
position: 6
---
# View Execution Status

The Execution Status view allows you to verify the state of the current project and whether it is connected to a configured Scheduling setup, or is running locally. The view provides additional details for the available Execution machines.

## Execution Status View Window

To access the Status view you can click **Status** in the **Scheduling** ribbon of the **Project** tab.

![Status][1]

## Locally Connected Project

If the current project is connected to execute tests locally, the Status view will provide details only for the local Scheduler and the Test Runner, in case this is not pointing to another machine configured as a Scheduling server.

![Status Window locally][2a]

Double click on the listed Execution machine will load additional details for the machine - available browsers with the option to calibrate these, access to the logging of that machine.

![Execution machine details locally][2b]

## Remotely Connected Project

The **Remote Execution Status Window** provides a summary of each Execution Server connected to this Scheduling Server and an overview for the Scheduling and Storage services.

![Status Window][2]

### Test Studio Services Possible Statuses

- **Scheduling Server** section shows if the service is running, which is the server URL and the version of Test Studio on that server machine.

- **Storage Server** sections shows if the service is running, which is the server URL and the version of Test Studio on that server machine. Along with that is displayed the database version and if its service is running.

- If any of the services is not running for some reason at least its status will be in red to indicate there is something wrong. If the **Scheduling Service** is down the Storage and Database will be also down.

![Status Window Scheduling Service Down][8]

- If the **Storage Service** is down the Scheduling service will still be alive but the Database will not be usable.

![Status Window Storage Service Down][9]

- If the **MongoDB service or the databse** is down only its status will be in red. 

![Status Window MongoDB Service Down][10]

### List of Execution Servers

- If there are not calibrated browsers on any of the remote machines the respective browser icon will be marked with a yellow warning sign. To calibrate it you could either drill down to the particular machine details or turn on the AutoCalibrateBrowsers setting in the <a  href="/getting-started/test-execution/test-list-settings#Web-Tab" target="_blank">Web tab of Test List Settings</a>. 

![Status Window Non-calibrated Browsers][4]

### Execution Servers Details

To view detailed information about an Execution Server, double-click the respective row in the grid or click the magnifier icon in front of the machine name. The **Execution Server Details** screen provides extended information about the specifications, system performance and test execution status of an Execution machine.

![Execution Server Details][3]

- The **Machine Information** section displays system specification for the machine.

- The **Browser Information** section displays all installed browsers on the execution machine along with their calibration state. All installed browsers on the remote machine could be calibrated or restored to default settings from the provided buttons - Calibrate and Restore.

- The **Logging information** section allows you to enable or disable the Logging on the Execution machine, View and Clear the Log.

### Execution Machine Possible Statuses

The **Execution Server Details** view displays different statuses for the selected execution machine as per its state

- If there are tests running on the machine only the buttons in the Logging sections will be enabled. The installed browsers could not be calibrated while tests are being executed.

![Running Tests][5]

- If the name of the currently executed test on an execution machine is too long it will be partially displayed. To see the whole string hover the mouse over the partially displayed one.

![Very Long Test Name][6]

- If the execution machine could not be accessed all buttons in the Browser and Logging sections will be disabled. A warning message appears to double check what could be preventing the connection to remote execution server. 

![Unreachable Execution Machine][7]

The Back button navigates back to the list with connected execution machines. 

[1]: /img/features/scheduling-test-runs/view-execution-status/fig1.png
[2]: /img/features/scheduling-test-runs/view-execution-status/fig2.png
[2a]: /img/features/scheduling-test-runs/view-execution-status/fig2a.png
[2b]: /img/features/scheduling-test-runs/view-execution-status/fig2b.png
[3]: /img/features/scheduling-test-runs/view-execution-status/fig3.png
[4]: /img/features/scheduling-test-runs/view-execution-status/fig2_nonCalibrated.png
[5]: /img/features/scheduling-test-runs/view-execution-status/fig3_runningTest.png
[6]: /img/features/scheduling-test-runs/view-execution-status/fig3_VeryLongNameTest.png
[7]: /img/features/scheduling-test-runs/view-execution-status/fig3_unreachableExecutionMachine.png
[8]: /img/features/scheduling-test-runs/view-execution-status/fig2_schedulingServiceDown.png
[9]: /img/features/scheduling-test-runs/view-execution-status/fig2_storageServiceDown.png
[10]: /img/features/scheduling-test-runs/view-execution-status/fig2_MongoServiceDown.png