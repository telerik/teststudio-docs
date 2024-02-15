---
title: Configure Test Studio Execution Server
page_title: Configure Test Studio Execution Server
description: "Create Test Studio Execution Server on a dedicated execution machine in a scheduling setup. Execute Test Studio tests on remote machines. The Execution Server is the Test Studio Test Runner instance of Test Studio Standalone installation or the Test Studio Run-Time Edition installation. An Execution Server is ready for use when configured and registered with your Scheduling Server."
position: 3
---
# Configure a Machine to Act as an Execution Server

Test Studio Execution Server can be any machine with installed Test Studio (<a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Run-time edition</a> is the minimum required). Configure the machine's Execution client to point to a running Scheduling service and it is registered as an Execution server for this Scheduler.

The below article describes the configuration steps.

* [Start the Execution Client](#start-the-execution-client)
* [Configure Test Studio Execution Client](#configure-test-studio-execution-client)
* [Browser Support Update](#browser-support-update)
* [User Session Configuration](#user-session-configuration)

## Start the Execution Client

The **Test Studio Execution Client** is the Run-time component of Test Studio. It gets installed with Test Studio Standalone and Run-time editions. To start the Execution Client, called also Test Runner, type in the __Windows Start Menu__ > **Start Execution Server**.

![Start Execution Server][1a]

The Execution client is running in the background, so if this is __already started__ (automatically on machine startup or automatically with a test project), you might get prompted that **The Test Runner is already running**. In this case you can access it from the __Windows Task Bar__ on the lower right corner - locate the Test Studio icon, right click on it and choose the **Show** option.

![Show][1]

## Configure Test Studio Execution Client

Once the **Test Studio Test Runner** window appears, there are multiple options you can customize as per the specifics of the particular environment.

* [Execution Server Configuration](#execution-server-configuration)
* [Machine Information](#machine-information)
* [Logging Information](#logging-information)
* [Run on Startup](#run-on-startup)
* [Browsers Information](#browsers-information)

### Execution Server Configuration

- **Status** - shows the current status of the Execution Server and if it can connect to the listed Scheduling server.

- **Scheduling URL** - shows the URL of the current Scheduling server to which the Execution server is connected. Use the **three dots button** next to the Scheduler name to **change the address** of Scheduling server to use.

    ![Change Location][2]

    Type in the **Scheduling Service URI** text field the Scheduling service machine with the correct port on which it's configured. Hit the **Change** button to connect to the listed Scheduling Server.

    ![Service URI][3]

- **Temp Folder** - executing tests on a remote machine includes deployment of the project files in a temporary folder on the remote machine. You can choose where this temp folder will be located on the disc - click the three dots button next to the listed folder and browse to the desired one. The **Reset** button will set the default temporary location on the execution machine.

![Temporary folder][5]

> **Note**
><br> 
><br> You need to allow access to the newly set location for all users.

- **Key** - the communication key is required to establish the connection and to enable the communication to the Scheduling server machine. A <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-services" target="_blank">key is generated in the Scheduling Config wizard</a> and if it's not matching on both the Scheduler and Execution machines, the connection between these is not possible. 

> **Note**
><br> 
><br> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

### Machine Information

The section contains details for the Execution Server machine - status, Test Studio version, machine name, OS version, machine stats.

![Machine Information][6]

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

### Logging Information

You can access the logging of the Execution Server - enable, disable or view <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">the generated log</a>.

![Logging Information][6a]

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

### Run on Startup

The **Run on start up** option allows you to decide whether the Test Runner should be started automatically on machine startup.

![Run on start up][7]

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

### Browsers Information

All available and supported browsers on the Execution Server are listed in this section. You can <a href="/features/project-settings/browsers" target="_blank">calibrate</a> these or restore their default settings. If using the legacy version of Edge, you can browse here the WebDriver folder location on disc.

![Browsers Information][6b]

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

## Browser Support Update

This section appears only if there is an <a href="/features/dialogs-and-popups/dialog-handler-updater" target="_blank">__update for latest browser versions__</a> and allows you to update these with a single button click.

![Dialog Handler Update][6c]

## User Session Configuration

Test Studio allows you to apply different configurations for the user session on the execution machines. That way you can make sure the machine is available and ready to execute UI tests.

![User session configuration][8]

### Keep Machine Awake

With this option enabled and as long as the Test Studio Scheduling Client process is running, it __prevents the machine from falling to sleep, locking or showing screen saver__.

> __Note!__ 
><br> 
><br> This functionality __does not prevent__ the user to manually lock the machine or put it to sleep.
><br> 
><br>
> __Note!__ 
><br> 
><br> Using this functionality could be a security risk since it will prevent the machine from locking when expected by your security policy. Consider if leaving the test machine unlocked for prolonged periods is acceptable for your organization before using the feature (especially when using Test Studio on your local physical machine).

Once the __option is disabled or the Test Studio Scheduling Client process is stopped__, the operating system is able to get to sleep/lock normally.

### Reconnect to Console on Disconnect

When running tests on a remote virtual or physical machine, users would usually connect to that machine via Remote Desktop Connection (RDC) to start and configure the Test Studio Scheduling Client. If after that the user closes their RDC window, their user session on the virtual machine is switched to 'disconnected' state and lose access to the graphical user interface (GUI). This prevents UI tests to be executed normally, whenever an interaction to the GUI is needed (e.g. performing real mouse click or keyboard actions, dialog interaction, etc.).

When the __'Reconnect to Console on Disconnect'__ feature is enabled, Test Studio tries __to reconnect your disconnected session to the local console session__, regaining access to the GUI.

> __Note!__ 
><br>
> In the case when there is a __physical monitor attached to the Execution machine__, the reconnected __console session gets displayed__ on it.
><br>
> That means if there is another user who has physical access to the machine, they will be able to view the screen or interact with it. Therefore consider carefully if that is acceptable for your organization before using the feature.
><br>
><br>
> __Note!__ 
><br>
> If you keep the __Remote Desktop Connection session open__ but minimized, the local console session isn't reconnected.
><br>
> If you need to run tests in <a href="/knowledge-base/test-execution-kb/minimized-rdc" target="_blank">minimized RDP window you can try modifying the Terminal Server Client registry keys as suggested</a>.

### Change Console Resolution

When the __'Reconnect to Console on Disconnect'__ feature is enabled, you have the option to change the __Console session resolution__ - you can choose the desired resolution from the dropdown menu. This option is useful when tests are executed on remote machine and successful test run depends on particular screen resolution. When set through the Test Studio Runner, you can ensure the automated tests are executed on the specified resolution.

## See Also

* <a href="https://www.telerik.com/blogs/improve-remote-test-execution-test-studio-user-session-configuration" target="_blank">Improve Your Remote Test Execution with Test Studio User Session Configuration</a>.

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