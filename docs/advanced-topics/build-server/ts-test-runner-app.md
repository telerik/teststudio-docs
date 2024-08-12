---
title: Test Studio Execution Client in CI Builds
page_title: Test Studio Execution Client in CI
description: "Use Test Studio Test Runner app to control the machine user session when running UI tests as part of CI pipeline. "
position: 3
---
# Test Studio Test Runner in CI Builds

The **Test Studio Execution Client** is the Run-time component of Test Studio. It gets installed both with the Test Studio Standalone and the Run-time editions. Part of its options are also applicable when running UI tests as part of a CI build pipelines.

This article guides you through the configuration of the Test Studio Execution Client when used in CI environment. 

## Start the Execution Client

To start the Execution Client, called also Test Runner, type in the __Windows Start Menu__ > **Start Execution Server**.

![Start Execution Server from Windows Start Menu][1a]

### Message "Test Runner is already running"

By default the Execution client is running in the background. Thus if the runner is __already started__ (automatically on machine startup, or automatically with a test project, or under another user session) and you try starting it you get prompted with a message that **The Test Runner is already running**. 

![Test Runner is already running][0]

In this case you can access it from the __Windows Task Bar__ on the lower right corner - locate the Test Studio icon, right click on it and choose the **Show** option. 

![Show Test Runner from system tray][1]

> __Note__
><br>
><br>
> If the Test Runner is started under another user session you need to stop its process and start it again under the current user session. 

## Run on Startup

The **Run on start up** option allows you to decide whether the Test Runner should be started automatically on machine startup.

![Run on start up][7]

## User Session Configuration

Test Studio allows you to apply different configurations for the user session on the execution machines. That way you can make sure the machine is available and ready to execute UI tests.

![User session configuration][8]

* [Keep Machine Awake](#keep-machine-awake)
* [Reconnect to Console on Disconnect](#reconnect-to-console-on-disconnect)
* [Change Console Resolution](#change-console-resolution)

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

## Use Test Studio Application Log

You can access the logging of the Execution Server - enable, disable or view <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">the generated log</a>.

![Logging Information][6a]

## Browsers Information

All available and supported browsers on the Execution Server are listed in this section. You can <a href="/features/project-settings/browsers" target="_blank">calibrate</a> these or restore their default settings. If using the legacy version of Edge, you can browse here the WebDriver folder location on disc.

![Browsers Information][6b]

<br>
<div><a style="float:right" href="#configure-test-studio-execution-client">Back to top of section</a></div>
<br>

## Browser Support Update

This section appears only if there is an <a href="/features/dialogs-and-popups/dialog-handler-updater" target="_blank">__update for latest browser versions__</a> and allows you to update these with a single button click.

![Dialog Handler Update][6c]


## See Also

* <a href="https://www.telerik.com/blogs/improve-remote-test-execution-test-studio-user-session-configuration" target="_blank">Improve Your Remote Test Execution with Test Studio User Session Configuration</a>.

[0]: /img/features/scheduling-test-runs/create-execution-server/fig0.png
[1]: /img/features/scheduling-test-runs/create-execution-server/fig1.png
[1a]: /img/features/scheduling-test-runs/create-execution-server/fig1a.png
[2]: /img/features/scheduling-test-runs/create-execution-server/fig2.png
[3]: /img/features/scheduling-test-runs/create-execution-server/fig3.png
[4]: /img/features/scheduling-test-runs/create-execution-server/fig4.png
[5]: /img/features/scheduling-test-runs/create-execution-server/fig5.png
[6]: /img/features/scheduling-test-runs/create-execution-server/fig6.png
[6a]: /img/features/scheduling-test-runs/create-execution-server/fig6a.png
[6b]: /img/features/scheduling-test-runs/create-execution-server/fig6b.png
[6c]: /img/features/scheduling-test-runs/create-execution-server/fig6c.png
[7]: /img/features/scheduling-test-runs/create-execution-server/fig7.png
[8]: /img/features/scheduling-test-runs/create-execution-server/fig8.png