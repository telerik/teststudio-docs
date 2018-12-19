---
title: Non-Domain Environment
page_title: Non-Domain Environment
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Scheduling in a Non-Domain And Cloud Environment#

I would like to use the Test Studio Scheduling feature in a non-domain environment.

This is possible, however there are several important steps you must take in addition to the standard Scheduling setup.

Basically the same rules apply here, the only difference is that machines are not in the same domain. This is the reason the scheduling and storage should be configured to use the machine's **IP addresses** instead of their host names. 

##Scheduling Server Configuration

1.&nbsp; Find in the Windows programs **Configure as Scheduling Server** application.

![Configure scheduling server][1]

2.&nbsp; In the dialog that appears click **MongoDB** tab. Verify MongoDB data path and mongod.exe path and hit Apply. Confirm the MongoDB is started status at lower left.

![Click connect][2]

> The **MongoDB** tab will be grayed out (inactive) if you do not have MongoDB installed on the machine!

3.&nbsp; In the **Storage** tab verify the connection string and hit Apply. Verify the Telerik Storage Service is started in the lower left. Use localhost if you have MongoDB installed on your local machine.

![Configure storage][3]

If you don't have MongoDB installed on the local machine you need to specify the remote machine **IP address** that has MongoDB installed. 

![Remote Storage Configuration][4]

In the **Scheduling** tab specify the storage service location and scheduling service URL with the **IP addresses** of the machines. Verify the Scheduling Service is running from lower left. Optionally you can configure Email (SMTP) server. This is in case you would like to receive scheduling result via email. 

![Configure Scheduling][8]

The scheduling is now configured. 

##Execution Server Configuration

We will have to configure the Execution server as well. Log in on the execution machine. You will need to have RunTime installed already.

Open the **Telerik.TestStudio.Scheduling.Client.exe.Config** located in:

**C:\ProgramData\Telerik\Configs**

*Note: ProgramData is a hidden folder.*

and replace the following two values with IP addresses instead of host names:

**ExecutionManagerUrl** - that should be the Scheduling service URL you have previously copied when configuring the Scheduling Server.

**ProcessManagerUrl** - that should be the IP address of the execution machine.

![Edit config][5]

You may now start the execution server:

Click **Start Menu > All Programs > Telerik > Test Execution 20XX.X > Start Execution Server**.

In the Windows Task Bar, right click the Test Studio icon and click **Show**


![Show button][6]

The Test Studio Test Runner dialog appears and it should look like the one below, configured with IP addresses and connected to the Scheduling:

![Test Runner][7]

[1]: /img/knowledge-base/scheduling-kb/non-domain-environment/fig1.png
[2]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[3]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[4]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png
[5]: /img/knowledge-base/scheduling-kb/non-domain-environment/fig5.png
[6]: /img/knowledge-base/scheduling-kb/non-domain-environment/fig6.png
[7]: /img/knowledge-base/scheduling-kb/non-domain-environment/fig7.png
[8]: /img/knowledge-base/scheduling-kb/non-domain-environment/fig8.png