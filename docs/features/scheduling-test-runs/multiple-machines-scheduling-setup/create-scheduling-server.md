---
title: Configure a Test Studio Scheduling Server
page_title: Configure a Test Studio Scheduling Server
description: "Create a Scheduling Server in Test Studio to be able to run schedule tests on remote machines. The Telerik scheduling service keeps track of what tests to run and sends this data to the execution servers. This is a centralized component to control the scheduled test list runs in the Test Studio Scheduling setup"
position: 1
---
# Configure a Machine to Act as a Scheduling Server

The Scheduling server in the Test Studio Scheduling setup is the centralized component in the setup, which controls the communication between all machines in the setup. It keeps track of what test lists from a project to run, sends this data to the execution servers and collects the generated results from the test list runs.

## Minimum Requirements for the Machine Hosting the Scheduling Service

Before proceeding, there are a few things to confirm regarding the computer you will be using as the Scheduling Server:

- The software must be run from a Windows Administrator account.
- User Account Control must be turned off completely (set to *Never notify*).
- The Scheduling Server requires a Test Studio Run-time installation or higher.

If you do not meet the above requirements, the software will not launch or will quit immediately.

## Install the Test Studio Scheduling Service

To configure a machine as a Scheduling server, you need to install **minimum the Test Studio Run-time edition** on this computer. Ensure to include the Scheduling Service component in the **Customize Installation dialog** in the installation wizard.

![Installation Dialog][1]

> **Note:** Configuring a Scheduling Server for remote execution requires the <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-storage-server" target="_blank">Test Studio Storage service</a> to be installed on any machine in the Scheduling environment, which is accessible from the Scheduling Server. These can be **hosted also on the same machine**.

## Configure the Test Studio Scheduling Service

Start Test Studio and under the *Project* tab in the *Scheduling* section, click **Configure** button.

![Configure][2]

Optionally, the **Configure Scheduling** wizard can be accessed through the Windows Start menu by typing *Configure Test Studio Services*.

![Configure scheduling setup wizard][2a]

### MongoDB Tab

In the dialog which appears, the first **MongoDB** tab contains the settings required for the Mongo database. The **MongoDB data path** and **mongod.exe path** fields are populated with the values for a default MongoDB installation, so you need to change these, **only if the MongoDB installation was modified**. Hit the **Apply** button and confirm the *MongoDB is started* status appears in the lower left corner of the wizard.

![MongoDB][6]

> **Note:** The **MongoDB** tab will be grayed out (inactive) if you do not have MongoDB installed on the machine! This will get enabled when the correct MongoDB connection string is set in the **Storage** tab.

### Storage Tab

The **Storage** tab displays the Test Studio Storage service details and location - you can verify the **MongoDB connection string**, which is the default way to connect to the Mongo database. Hit the **Apply** button and check the *Telerik Storage Service is started* status appears in the lower left corner of the wizard.

![Storage][7]

> **Note:** If the **Test Studio Storage Service and MongoDB** are installed on any of the other machines in the Scheduling setup, the **MongoDB connection string** need to be modified to point to the particular machine.

*'localhost'* is used when the same machine hosts both the Scheduling and Storage services and MongoDB. If **MongoDB is installed on another machine** you need to specify that remote machine name.

![Storage][8]

### Scheduling Tab

The **Scheduling** tab contains information about the location of the Test Studio Storage and Scheduling services. The default populated values are pointing to the local machine - *'localhost'*. If the Test Studio services are hosted on different machine, here you can enter the respective machine names or IPs. Once ready. you can hit the **Apply** button. An informational message appears in the lower left corner of the wizard stating *'Telerik Scheduling Service is running'*.

![Scheduling][9]

Optionally, you can configure the Test Studio Scheduling service to use an Email (SMTP) server by specifying few additional details. These settings allow you to <a href="/features/scheduling-test-runs/schedule-execution#step-3" target="_blank">send an automatic email</a> with the results of a scheduled test list. Depending on the SMTP server configuration, mandatory fields are the *'SMTP server address'* and the *'Port'* to communicate with it and the *'User Email'* and *'Password'* are not explicitly required. Once these fields are populated, hit the **Apply** button to reflect the changes to the Scheduling service and check if the *'Telerik Scheduling Service is running'* appears in the lower left corner of the wizard.

![Scheduling SMTP][9a]

### Executive Dashboard Tab

In the <a href="/general-information/test-results/executive-dashboard" target="_blank">**Executive Dashboard** tab</a> verify which is the address to access the results from the scheduled runs.

Close the dialog window and your scheduling setup is finished.

[1]: /img/features/scheduling-test-runs/create-storage-server/fig1.png

[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[2a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2a.png

[6]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[7]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[8]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png
[9]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png
[9a]: /img/features/scheduling-test-runs/create-scheduling-server/fig5a.png