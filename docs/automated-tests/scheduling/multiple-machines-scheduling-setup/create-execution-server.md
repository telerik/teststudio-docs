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

<!-- no toc -->
* [Execution Server Configuration](#execution-server-configuration)
* [Machine Information](#machine-information)
* [Logging Information](#logging-information)
* [Browsers Information](#browsers-information)

### Execution Server Configuration

The configuration of the Test Studio Test Runner requires admin rights and is performed through the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Test Studio Services config wizard</a>. Use the __Configure__ button to open the wizard showing its <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#execution-server-tab" target="_blank">Execution server tab</a> and apply any necessary changes. 

![Configure button to open Execution server config][2a]

- **Status** - shows the current status of the Execution Server and if it can connect to the listed Scheduling server.

- **Scheduling URL** - shows the URL of the current Scheduling server to which the Execution server is connected.  

- **Temp Folder** - executing tests on a remote machine includes deployment of the project files in a temporary folder on the remote machine. You can choose where this temp folder will be located on the disc - the default location is the %PUBLIC% folder which is accessible for all users. 

    > **Note**
    ><br> 
    ><br> If you want to change the temp folder be sure to allow access to the newly set location for all users.

- **Key** - the communication key is required to establish the connection and to enable the communication to the Scheduling server machine. A <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-services" target="_blank">key is generated in the Scheduling Config wizard</a> and if it's not matching on both the Scheduler and Execution machines, the connection between these is not possible. 

    > **Note**
    ><br> 
    ><br> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.

- **Run on start up** - the option allows you to decide whether the Test Runner should start automatically on machine startup.

![Execution server configuration][2]

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

Test Studio requires active user session for executing functional UI tests such as automated tests for WPF and desktop application, and web tests executed in headful browser mode. 

To help in covering this requirement Test Studio provides a separate application which is dedicated to keep the machine awake and with active user session. The application is called __Test Studio Session Monitor__ and you can start it as follows: 

- From the Windows start menu by typing _Session Monitor_.
  
    ![Start Session Monitor from Win menu][8a]

- From the Test Studio Test Runner by clicking the __Configure__ button in the __User Session Configuration__ section. 
    ![Start Session Monitor from Test Runner][8b]

> __Note!__ 
><br> 
> Running and configuring the separate application Test Studio Session Monitor requires admin rights. 

![Session Monitor application][8]

### Keep Machine Awake

Enabling this option __prevents the machine from falling to sleep, locking or showing screen saver__. The setting is applied as long as the __Test Studio Session Monitor__ application is running in the background. 

![Keep Machine awake][9]

> __Note!__ 
><br> 
> This functionality __does not prevent__ the user to manually lock the machine or put it to sleep.
><br> 
><br>
> __Note!__ 
><br> 
> Using this functionality could be a security risk since it will prevent the machine from locking when expected by your security policy. Consider if leaving the test machine unlocked for prolonged periods is acceptable for your organization before using the feature (especially when using Test Studio on your local physical machine).

Once the __option is disabled or the Test Studio Session Monitor process is stopped__, the operating system is able to get to sleep/lock normally.

### Reconnect to Console on Disconnect

When running tests on a remote virtual or physical machine, users would usually connect to that machine via Remote Desktop Connection (RDC) to start and configure the Test Studio Execution Server. Closing the RDC window sets the user session on the virtual machine to 'disconnected' state and the access to the graphical user interface (GUI) is lost. This prevents UI tests to be executed normally, whenever an interaction to the GUI is needed (e.g. performing real mouse click or keyboard actions, dialog interaction, etc.).

When the __'Reconnect to Console on Disconnect'__ feature is enabled, Test Studio Session Monitor app tries __to reconnect your disconnected session to the local console session__, regaining access to the GUI.

![Reconnect to console][10]

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

![Change Console Resolution][11]

### Run on Startup 

The Run on start up option allows you to decide whether the Test Studio Session Monitor starts automatically on machine startup. We recommend using the option if this is the tool you use to control the user session. 

![Run Session Monitor on startup][12]

## See Also

* <a href="https://www.telerik.com/blogs/improve-remote-test-execution-test-studio-user-session-configuration" target="_blank">Improve Your Remote Test Execution with Test Studio User Session Configuration</a>.

[1]: /img/features/scheduling-test-runs/create-execution-server/fig1.png
[1a]: /img/features/scheduling-test-runs/create-execution-server/fig1a.png
[2]: /img/features/scheduling-test-runs/create-execution-server/fig2.png
[2a]: /img/features/scheduling-test-runs/create-execution-server/fig2-configure-button.png
[3]: /img/features/scheduling-test-runs/create-execution-server/fig3.png
[4]: /img/features/scheduling-test-runs/create-execution-server/fig4.png
[5]: /img/features/scheduling-test-runs/create-execution-server/fig5.png
[6]: /img/features/scheduling-test-runs/create-execution-server/fig6.png
[6a]: /img/features/scheduling-test-runs/create-execution-server/fig6a.png
[6b]: /img/features/scheduling-test-runs/create-execution-server/fig6b.png
[6c]: /img/features/scheduling-test-runs/create-execution-server/fig6c.png
[7]: /img/features/scheduling-test-runs/create-execution-server/fig7.png
[8]: /img/features/scheduling-test-runs/create-execution-server/fig8.png
[8a]: /img/features/scheduling-test-runs/create-execution-server/start-session-monitor-win-menu.png
[8b]: /img/features/scheduling-test-runs/create-execution-server/start-session-monitor-config.png
[9]: /img/features/scheduling-test-runs/create-execution-server/fig9.png
[10]: /img/features/scheduling-test-runs/create-execution-server/fig10.png
[11]: /img/features/scheduling-test-runs/create-execution-server/fig11.png
[12]: /img/features/scheduling-test-runs/create-execution-server/fig12.png