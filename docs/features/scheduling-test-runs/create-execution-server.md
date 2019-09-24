---
title: Create an Execution Server
page_title: Create an Execution Server
description: "Create a Test Studio Execution Server on a dedicated execution machine in a scheduling setup. Execute Test Studio tests on remote machines. The Execution Server is the Test Studio Test Runner instance of Test Studio Standalone installation or the Test Studio Run-Time Edition installation. An Execution Server is ready for use when configured and registered with your Scheduling Server."
previous_url: /user-guide/scheduling-test-runs/create-an-execution-server.aspx, /user-guide/scheduling-test-runs/create-an-execution-server
position: 6
---
# Create an Execution Server

The Execution Server is the Test Studio Test Runner instance of Test Studio Standalone installation or the Test Studio Run-Time Edition installation. An Execution Server is ready for use when configured and registered with your Scheduling Server. Because of this, first is required a successfully <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">configured Scheduling Server</a>. 

An Execution Server (ES) could be a physical or virtual machine. Multiple Execution Servers could be connected to a single Scheduling Server (SS) to allow you to execute multiple test lists simultaneously. Differences in operating systems between the machines running the SS and the ES are allowed. Though, each ES **must be running the same version of Test Studio** as the SS. 

Few things to consider when choosing an ES machine:

- An active and unlocked desktop session is required - you must be logged on with an Administrator account at all times, you can disconnect from the ES but not log off.
- Ensure that the Execution Server machine has sufficient space on disk to store a copy of any project you schedule for execution on that Execution Server.
- If you plan to use 'Get Latest from TFS' on scheduled test runs, make sure the Test Studio Execution Server is running under an account with access to log on to the TFS repository.

After successfully installing Test Studio Standalone or Test Studio Run-Time, run the Execution server software:

1.&nbsp; Click **Start Menu** > **All Programs** > **Telerik** > **Test Execution 20XX.X** > **Start Execution Server**.

2.&nbsp; In the Windows Task Bar, right click the Test Studio icon and click **Show**.

![Show][1]

3.&nbsp; The **Test Studio Test Runner** dialog appears. The address for the Scheduling Server that the Execution Server is connected to appears under **Execution Server Configuration**. To change this address, click the Change button ![Change button][4] next to the Scheduling service address.

![Change Location][2]

If there is no Change button ![Change button][4] this is <a href="/troubleshooting-guide/scheduling-issues-tg/no-change-button" target="_blank">how to resolve this</a>.

4.&nbsp; Type the address for the Scheduling Service under **Scheduling Service URI** and click on Change to connect to the Scheduling Server

![Service URI][3]

5.&nbsp; As of release **R1 2018 (v.2018.1.301)** the temporary folder where the project is downloaded on the execution machine for a remote(either scheduled or not) run could be configured to any other folder on the remote machine. Click the Change button ![Change button][4] next to the temp folder path and browse to the desired folder. 

![Temporary folder][5]

The *Reset* button will set the default temporary location on the execution machine. 

>It is important to allow access to the newly set location  for all users. 

6.&nbsp; As of release **R1 2018 (v.2018.1.301)** the Execution tab of the Test Runner contains details for the machine and OS, installed browsers and if these are <a href="/features/project-settings/browsers" target="_blank">calibrated</a>, provides access to <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">the logging</a> on that execution machine and the ability to set the <a href="/getting-started/configure-your-browser/edge" target="_blank">MS Edge Web Driver folder location</a>. This will easily allow you to modify these if logged on the execution machine.

![Additional Information][6]

7.&nbsp; If the **Run on start up** checkbox ic checked the the Execution Server will be automatically started on Windows startup.

![Run on start up][7]

## User Session Configuration

Test Studio allows you to apply different configurations for the user session on the execution machines. That way you can make sure the machine is available and ready to execute UI tests.

![User session configuration][8]

### Keep Machine Awake

If this option is enabled, as long as the Test Studio Scheduling Client process is running, it will prevent your machine from falling to sleep, locking or showing screensaver. This will prevent them from breaking your UI tests.

Once the option is disabled or the Test Studio Scheduling Client process is stopped, the operating system will be able to get to sleep/lock normally.

> __Note:__ This functionality will not prevent the user to manually lock the machine or put it to sleep.
</br>
> __Note:__ Using this functionality could be a security risk since it will prevent the machine from locking when expected by your security policy. Please consider if leaving the test machine unlocked for prolonged periods is acceptable for your organization before using the feature (especially when using Test Studio on your local physical machine).

### Reconnect to Console on Disconnect

When running tests on a remote virtual or physical machine, users would usually connect to that machine via Remote Desktop Connection (RDC) to start and configure the Test Studio Scheduling Client. If after that the user closes their RDC window, their user session on the virtual machine will be switched to 'disconnected' state and will lose access to the graphical user interface (GUI). This will prevent UI tests to be executed normally, whenever an interaction to the GUI is needed (e.g. performing real mouse click or keyboard actions, dialog interaction, etc.).

When the 'Reconnect to Console on Disconnect' feature is enabled, Test Studio will try to reconnect your disconnected session to the local console session, regaining access to the GUI.

> __Note:__ When your session gets connected to the local console session, if there is a physical monitor, attached to the Windows machine, your session will be displayed on it. If there is another user, that has physical access to the machine, they will be able to view your screen or interact with it. This could be a security issue, so please consider carefully if that is acceptable for your organization before using the feature.
</br>
> __Note:__ This feature will not have effect if you keep your Remote Desktop Connection session open, but minimized. You can see <a href="/knowledge-base/test-execution-kb/minimized-rdc" target="_blank">this article</a> for information on handling this case.

__See Also:__ You may find additional notes on the topic in our blog post Improve <a href="https://www.telerik.com/blogs/improve-remote-test-execution-test-studio-user-session-configuration" target="_blank">__Your Remote Test Execution with Test Studio User Session Configuration__</a>.

[1]: /img/features/scheduling-test-runs/create-execution-server/fig1.png
[2]: /img/features/scheduling-test-runs/create-execution-server/fig2.png
[3]: /img/features/scheduling-test-runs/create-execution-server/fig3.png
[4]: /img/features/scheduling-test-runs/create-execution-server/change-button.png
[5]: /img/features/scheduling-test-runs/create-execution-server/fig4.png
[6]: /img/features/scheduling-test-runs/create-execution-server/fig6.png
[7]: /img/features/scheduling-test-runs/create-execution-server/fig7.png
[8]: /img/features/scheduling-test-runs/create-execution-server/fig8.png