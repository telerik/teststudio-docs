---
title: Create a Scheduling Server
page_title: Create a Scheduling Server
description: "Create a Scheduling Server in Test Studio to be able to run schedule tests on remote machines. The Telerik scheduling service keeps track of what tests to run and sends this data to the execution servers."
previous_url: /user-guide/scheduling-test-runs/create-a-scheduling-server.aspx, /user-guide/scheduling-test-runs/create-a-scheduling-server
position: 5
---
# Create a Scheduling Server

The scheduling server keeps track of what tests to run and sends this data to the execution servers.

Before proceeding, there are a few things to confirm regarding the computer you will be using as the Scheduling Server:

- The software must be run from a Windows Administrator account.
- User Account Control must be turned off completely (set to *Never notify*).
- The Scheduling Server requires a Test Studio Runtime installation or higher.

If you do not meet the above requirements, the software will not launch or will quit immediately. 

> Configuring a Scheduling Server for remote execution requires that you <a href="/features/scheduling-test-runs/overview" target="_blank">install the Storage Service</a> on a machine you can access from the Scheduling Server.
> If the Scheduling Server has a Standalone installation, enable the <a href="/getting-started/installation/install-procedure" target="_blank">Scheduling Component</a>.

1.&nbsp; Open Test Studio. In the top navigation menu click the **Configure** button in the Scheduling ribbon.

![set][5]

2.&nbsp; In the dialog that appears click **MongoDB tab**. Verify **MongoDB data path** and **mongod.exe path** and hit **Apply**. Confirm the *MongoDB is started* status at lower left.

![MongoDB][6]

> The **MongoDB** tab will be grayed out (inactive) if you do not have MongoDB installed on the machine!

3.&nbsp; In the **Storage** tab verify the connection string and hit **Apply**. Verify the Telerik Storage Service is started in the lower left.

![Storage][7]

If you don't have MongoDB installed on the local machine you need to specify the remote machine name that has MongoDB installed. See highlighted.

![Storage][8]

4.&nbsp; In the Scheduling tab verify the information displayed and click **Apply**. Verify the Scheduling Service is running from lower left. Optionally you can configure Email (SMTP) server. This is in case you would like to receive scheduling result via email.

![Scheduling][9]

Close the dialog window and your scheduling setup is finished.

[5]: /img/features/scheduling-test-runs/create-scheduling-server/fig1new.png
[6]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[7]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[8]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png
[9]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png