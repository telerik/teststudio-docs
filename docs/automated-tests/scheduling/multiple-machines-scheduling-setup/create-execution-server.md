---
title: Configure a Test Studio Execution Server
page_title: Configure a Test Studio Execution Server
description: "Create a Test Studio Execution Server on a dedicated execution machine in a scheduling setup. Execute Test Studio tests on remote machines. The Execution Server is the Test Studio Test Runner instance of Test Studio Standalone installation or the Test Studio Run-Time Edition installation. An Execution Server is ready for use when configured and registered with your Scheduling Server."
position: 3
---
# Configure a Machine to Act as an Execution Server

The Test Studio Execution Server is the **Test Runner** instance of Test Studio Standalone installation or the Test Studio Run-Time Edition installation. An Execution Server is ready for use when configured and registered with your Scheduling Server. Because of this, the first requirement to cover is to successfully <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">configure a Scheduling Server</a>.

An Execution Server (ES) could be any physical or virtual machine. Multiple Execution Servers could be connected to a single Scheduling Server (SS) to allow you to execute multiple test lists simultaneously. Differences in operating systems and browsers between the machines running the SS and the ES are allowed. Though, **each ES must be running the same version of Test Studio as the SS**.

## Specific Requirements for an Execution Server Machine

Few things to consider when choosing an ES machine:

- An active and unlocked desktop session is required - you must be logged on with an Administrator account at all times, you can disconnect from the ES but not log off.  <a href="/knowledge-base/test-execution-kb/locked-machine" target="_blank">This article</a> explains further details on the topic.
- Ensure that the Execution Server machine has sufficient space on disk to store a copy of any project you schedule for execution on that Execution Server.
- If you plan to use 'Get Latest from TFS' on scheduled test runs, make sure the Test Studio Execution Server is running under an account with access to log on to the TFS repository.

## Install Test Studio Test Runner

The **Test Studio Test Runner** gets installed with a standard Test Studio Standalone product installation or Test Studio Run-Time Edition installation. To start the Test Runner, type in the Windows Start Menu > **Start Execution Server**.

![Start Execution Server][1a]

If you get prompted that **the Test Runner is already running**, you can right click the Test Studio icon in the Windows Task Bar and click **Show**.

![Show][1]

## Configure Test Studio Test Runner

Once the **Test Studio Test Runner** window appears, there are multiple options you can customize as per the specifics of the particular environment. 

### Execution Server Configuration

- **Status** - shows the current status of the Execution Server and if it is connected to the listed Scheduling server.

- **Scheduling URL** - shows the URL of the current configured Scheduling server, to which the Execution server is connected. To change this address, click the *'Change'* button (the three dots button) next to the listed Scheduling service address.

![Change Location][2]

Type the address for the machine which hosts the Scheduling Service under **Scheduling Service URI** with the correct port it is configured on and click on *'Change'* to connect to that Scheduling Server.

![Service URI][3]

- **Temp Folder** - the process of executing tests on a remote machine includes deployment of the project files in a temporary folder. You can choose where this temp folder will be located on the disc - click the *'Change'* button (the three dots button) next to the listed folder and browse the desired one. The *Reset* button will set the default temporary location on the execution machine.

![Temporary folder][5]

> **Note!** It is important to allow access to the newly set location for all users.

### Machine Information

The section contains details for the Execution Server machine - status, Test Studio version, machine name, OS version, machine stats.

![Machine Information][6]

### Logging Information

You can access the logging of the Execution Server - enable, disable or view <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">the generated log</a>.

![Logging Information][6a]

### Browsers Information

All available and supported browsers on the Execution Server are listed in this section. You can <a href="/features/project-settings/browsers" target="_blank">calibrate</a> these or restore their default settings. If using the legacy version of Edge, you can browse here the WebDriver folder location on disc.

![Browsers Information][6b]

## Browser Support Update

This section appears only if there is an <a href="/features/dialogs-and-popups/dialog-handler-updater" target="_blank">__update for latest browser versions__</a> and allows you to update these with a single button click.

![Dialog Handler Update][6c]

### Run on Startup

The **Run on start up** option allows you to decide whether the Test Runner should be started automatically on machine startup.

![Run on start up][7]

## User Session Configuration

Test Studio allows you to apply different configurations for the user session on the execution machines. That way you can make sure the machine is available and ready to execute UI tests.

![User session configuration][8]

### Keep Machine Awake

If this option is enabled, as long as the Test Studio Scheduling Client process is running, it will prevent your machine from falling to sleep, locking or showing screen saver. This will prevent them from breaking your UI tests.

Once the option is disabled or the Test Studio Scheduling Client process is stopped, the operating system will be able to get to sleep/lock normally.

> __Note!__ This functionality will not prevent the user to manually lock the machine or put it to sleep.</br>

> __Note!__ Using this functionality could be a security risk since it will prevent the machine from locking when expected by your security policy. Please consider if leaving the test machine unlocked for prolonged periods is acceptable for your organization before using the feature (especially when using Test Studio on your local physical machine).

### Reconnect to Console on Disconnect

When running tests on a remote virtual or physical machine, users would usually connect to that machine via Remote Desktop Connection (RDC) to start and configure the Test Studio Scheduling Client. If after that the user closes their RDC window, their user session on the virtual machine will be switched to 'disconnected' state and will lose access to the graphical user interface (GUI). This will prevent UI tests to be executed normally, whenever an interaction to the GUI is needed (e.g. performing real mouse click or keyboard actions, dialog interaction, etc.).

When the *'Reconnect to Console on Disconnect'* feature is enabled, Test Studio will try to reconnect your disconnected session to the local console session, regaining access to the GUI.

> __Note!__ When your session gets connected to the local console session, if there is a physical monitor, attached to the Windows machine, your session will be displayed on it. If there is another user, that has physical access to the machine, they will be able to view your screen or interact with it. This could be a security issue, so please consider carefully if that is acceptable for your organization before using the feature.</br>

> __Note!__ This feature will not have effect if you keep your Remote Desktop Connection session open, but minimized. You can see <a href="/knowledge-base/test-execution-kb/minimized-rdc" target="_blank">this article</a> for information on handling this case.

### Change Console Resolution

When the *'Reconnect to Console on Disconnect'* feature is enabled, you have the option to change the Console session resolution - you can choose the desired resolution from the dropdown menu. This option is useful when tests are executed on remote machine and successful test run depends on particular screen resolution. When set through the Test Studio Runner, you can ensure the automated tests will be executed on the specified resolution.

__See Also:__ You may find additional notes on the topic in our blog post Improve <a href="https://www.telerik.com/blogs/improve-remote-test-execution-test-studio-user-session-configuration" target="_blank">__Your Remote Test Execution with Test Studio User Session Configuration__</a>.

[1]: /img/features/scheduling-test-runs/create-execution-server/fig1.png
[1a]: /img/features/scheduling-test-runs/create-execution-server/fig1a.png
[2]: /img/features/scheduling-test-runs/create-execution-server/fig2.png
[3]: /img/features/scheduling-test-runs/create-execution-server/fig3.png
[4]: /img/features/scheduling-test-runs/create-execution-server/change-button.png
[5]: /img/features/scheduling-test-runs/create-execution-server/fig4.png
[6]: /img/features/scheduling-test-runs/create-execution-server/fig6.png
[6a]: /img/features/scheduling-test-runs/create-execution-server/fig6a.png
[6b]: /img/features/scheduling-test-runs/create-execution-server/fig6b.png
[6c]: /img/features/scheduling-test-runs/create-execution-server/fig6c.png
[7]: /img/features/scheduling-test-runs/create-execution-server/fig7.png
[8]: /img/features/scheduling-test-runs/create-execution-server/fig8.png