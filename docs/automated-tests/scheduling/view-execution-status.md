---
title: Machines Status View 
page_title: Scheduling Machines Status View
description: "Test Studio Scheduling Machines Status view. View the status of the Test Studio Execution Servers connected to a Test Studio Scheduling Server. Access the execution machines details and logging from the Test Studio Project"
position: 6
---
# Machines Status View

The Execution Status View is a useful source of information for the current status of a Scheduling setup. You can find out if a project is connected to a <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured Scheduling service</a>, or it is set to run only locally. For projects, which are connected to a Scheduling service, you can find additional details for <a href="#remotely-connected-project">the Test Studio services state</a> and the <a href="#list-of-execution-servers">currently registered Execution machines</a>.

* [Open Machines Status View Window](#machines-status-view-window)
* [Locally Connected Project](#locally-connected-project)
* [Remotely Connected Project](#remotely-connected-project)
* [Connect Project via Proxy Server](#connect-project-via-reverse-proxy-advanced)

## Machines Status View Window

To access the Status view you can click **Machines** in the **Scheduling** ribbon of the **Project** tab.

![Status][1]

## Connect Project Locally 

When current project is connected to schedule test lists locally, the **Machines Status** view provides details only for the local service status under the **Scheduling server** section.

![Machines Status for Locally connected project][2a]

The local Test Runner running in the system tray is listed under the **Execution Servers** section. Use the **Magnifier** icon or **double click the machine name** to open the view with additional details for the execution client - available browsers with the option to calibrate these, access to the logging of that machine.

![Execution machine details locally][2b]

## Connect Project Remotely

When current project is connected to schedule test lists remotely, the **Remote Execution Status Window** provides an overview for the Scheduling and Storage services and a list of all Execution Servers connected to this Scheduling Server.

![Status Window][2]

* [Test Studio Services Possible Statuses](#test-studio-services-possible-statuses)
* [List of Execution Servers](#list-of-execution-servers)
* [Execution Servers Details](#execution-servers-details)
* [Execution Machine Possible Statuses](#execution-machine-possible-statuses)

### Test Studio Services Possible Statuses

- **Scheduling Server** section shows if the service is running, which is the server URL and the version of Test Studio on that server machine.

- **Storage Server** sections shows if the service is running, which is the server URL and the version of Test Studio on that server machine. Along with that is displayed the database version and if its service is running.

- If any of the services is not running for some reason its status is highlighted in red to indicate that there is something wrong. If the **Scheduling Service** is down the Storage and Database are also down.

![Status Window Scheduling Service Down][8]

- If the **Storage Service** is down, the Scheduling service remains alive but the Database is not usable.

![Status Window Storage Service Down][9]

- If the **MongoDB service or the database** is down only its status is highlighted in red. 

![Status Window MongoDB Service Down][10]

<br>
<div><a style="float:right" href="#remotely-connected-project">Back to top of section</a></div>
<br>

### List of Execution Servers

- If any of the available browsers on the remote machines are not calibrated, the respective browser icon will be marked with a yellow warning sign. Double click that machine to open its details and calibrate the browser.

![Status Window Non-calibrated Browsers][4]

> **Tip**
><br> 
><br> To ensure executing browser is always calibrated you can use the `AutoCalibrateBrowsers` test list setting which is under the <a  href="/getting-started/test-execution/test-list-settings#web-tab" target="_blank">Web tab</a>.

- When an <a  href="/features/dialogs-and-popups/dialog-handler-updater" target="_blank">update for the latest browser versions</a> is available, a warning icon appears in front of the browsers' icons. To update Test Studio for the latest browsers on this execution server, open the <a  href="/automated-tests/scheduling/view-execution-status#execution-servers-details" target="_blank">machine details in the Execution status view</a> and use the __Update__ button.

![Status Window browser support Update][4a]

> **Tip**
><br> 
><br> The same __Update__ button is also available in the Test Runner application on the remote machine. So, you can logon on the machine and open its <a  href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-execution-server#browser-support-update" target="_blank">Execution client and update the installation for latest browser support</a>.

<br>
<div><a style="float:right" href="#remotely-connected-project">Back to top of section</a></div>
<br>

### Execution Servers Details

To view detailed information about an Execution Server, double-click the respective row in the grid or click the magnifier icon in front of the machine name. The **Execution Server Details** screen provides extended information about the specifications, system performance and test execution status of an Execution machine.

![Execution Server Details][3]

- The **Machine Information** section displays system specification for the machine.

- The **Browser Support Update** section notifies for the current state for browser support on the machine. If this needs to be updated, a warning sign notifies an update is available.

- The **Browser Information** section displays all installed browsers on the execution machine along with their calibration state. All installed browsers on the remote machine could be calibrated or restored to default settings from the provided buttons - Calibrate and Restore.

- The **Logging information** section allows you to enable or disable the Logging on the Execution machine, View and Clear the Log.

<br>
<div><a style="float:right" href="#remotely-connected-project">Back to top of section</a></div>
<br>

### Execution Machine Possible Statuses

The **Execution Server Details** view displays different statuses for the selected execution machine as per its state

- If there are tests running on the machine only the buttons in the Logging sections will be enabled. The installed browsers could not be calibrated while tests are being executed.

![Running Tests][5]

- If the name of the currently executed test on an execution machine is too long it will be partially displayed. To see the whole string hover the mouse over the partially displayed one.

![Very Long Test Name][6]

- If the execution machine could not be accessed all buttons in the Browser and Logging sections will be disabled. A warning message appears to double check what could be preventing the connection to remote execution server.

![Unreachable Execution Machine][7]

The Back button navigates back to the list with connected execution machines.

<br>
<div><a style="float:right" href="#remotely-connected-project">Back to top of section</a></div>
<br>

## Connect Project via Reverse Proxy (Advanced)

When current project is connected to schedule test lists remotely via Proxy Server, the **Remote Execution Status Window** provides an overview for the Scheduling and Storage services configured behind the proxy and a list of all Execution Servers connected to this Scheduling Server also hosted behind the proxy.

![Remote status via proxy server connection](/img/features/scheduling-test-runs/view-execution-status/fig4.png)

[1]: /img/features/scheduling-test-runs/view-execution-status/fig1.png
[2]: /img/features/scheduling-test-runs/view-execution-status/fig2.png
[2a]: /img/features/scheduling-test-runs/view-execution-status/fig2a.png
[2b]: /img/features/scheduling-test-runs/view-execution-status/fig2b.png
[3]: /img/features/scheduling-test-runs/view-execution-status/fig3.png
[4]: /img/features/scheduling-test-runs/view-execution-status/fig2_nonCalibrated.png
[4a]: /img/features/scheduling-test-runs/view-execution-status/fig2_dialogHandlerUpdate.png
[5]: /img/features/scheduling-test-runs/view-execution-status/fig3_runningTest.png
[6]: /img/features/scheduling-test-runs/view-execution-status/fig3_VeryLongNameTest.png
[7]: /img/features/scheduling-test-runs/view-execution-status/fig3_unreachableExecutionMachine.png
[8]: /img/features/scheduling-test-runs/view-execution-status/fig2_schedulingServiceDown.png
[9]: /img/features/scheduling-test-runs/view-execution-status/fig2_storageServiceDown.png
[10]: /img/features/scheduling-test-runs/view-execution-status/fig2_MongoServiceDown.png