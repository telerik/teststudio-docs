---
title: Remote Scheduled Execution (Single Machine Setup)
page_title: Remote Scheduled Execution
description: "Test Studio can be configured to run tests and test lists on remote execution machines. Scheduling setup. Telerik Scheduling Storage service"
position: 3
---
# Remote Scheduled Execution (Single Machine Setup)

With Test Studio you can schedule test lists on a single machine, but using the Test Studio services and simulating remote test list execution. The Scheduling service setup allows you to keep the generated results in a storage database. The below article describe the necessary steps to enable remote scheduling for a Standalone Test Studio installation on a single machine. You can watch a <a href="http://www.telerik.com/automated-testing-tools/support/videos/best-practices/how-to-setup-test-studio-remote-execution.aspx" target="_blank">video tutorial</a> for the same.

## Installing Test Studio for Remote Scheduled Execution

1.&nbsp; Install Test Studio product and ensure to <a href="/getting-started/installation/install-procedure" target="_blank">include the Telerik Scheduling Service and Telerik Storage Service components</a> in the **Customize Installation dialog**. The Test Studio services can be also added by <a href="/general-information/installation/add-services" target="_blank">changing the already installed product</a>.

![Installation Dialog][1]

> **Note:** The **Storage service** uses <a href="https://www.mongodb.com/" target="_blank">**MongoDB**</a> as a storage database and the Test Studio installation wizard automatically detects if the third party tool is already installed. If not it will also be installed. </br>
</br>
</br>

> **Note:** The Test Studio services are **not selected** in a default Test Studio Standalone installation and **are installed by default** when installing the Run-time Test Studio edition.

## Configure the Test Studio Services

Start Test Studio and under the *Project* tab in the *Scheduling* section, click **Configure** button.

![Configure][2]

Optionally, the **Configure Scheduling** wizard can be accessed through the Windows Start menu by typing *Configure Test Studio Services*.

![Configure scheduling setup wizard][2a]

### MongoDB Tab

In the dialog which appears, the first **MongoDB** tab contains the settings required for the Mongo database. The **MongoDB data path** and **mongod.exe path** fields are populated with the values for a default MongoDB installation, so you need to change these, **only if the MongoDB installation was modified**. Hit the **Apply** button and confirm the *MongoDB is started* status appears in the lower left corner of the wizard.

![MongoDB][11]

### Storage Tab

The **Storage** tab displays the Test Studio Storage service details - you can verify the **MongoDB connection string**, which is the default way to connect to the Mongo database. Hit the **Apply** button and check the *Telerik Storage Service is started* status appears in the lower left corner of the wizard.

![Storage][12]

### Scheduling Tab

The **Scheduling** tab contains information about the location of the Test Studio Storage and Scheduling services. The default populated values are pointing to the local machine - *localhost*. For this particular configuration, these can remain unchanged and you can hit the **Apply** button. An informational message appears in the lower left corner of the wizard stating *'Telerik Scheduling Service is running'*.

![Scheduling][13]

Optionally, you can configure the Test Studio Scheduling service to use an Email (SMTP) server by specifying few additional details. These settings allow you to <a href="/features/scheduling-test-runs/schedule-execution#step-3" target="_blank">send an automatic email</a> with the results of a scheduled test list. Depending on the SMTP server configuration, mandatory fields are the *'SMTP server address'* and the *'Port'* to communicate with it and the *'User Email'* and *'Password'* are not explicitly required. Once these fields are populated, hit the **Apply** button to reflect the changes to the Scheduling service and check if the *'Telerik Scheduling Service is running'* appears in the lower left corner of the wizard.

![Scheduling SMTP][13a]

### Executive Dashboard Tab

In the <a href="/general-information/test-results/executive-dashboard" target="_blank">**Executive Dashboard** tab</a> verify which is the address to access the results from the scheduled runs.

## Configure the Execution Client

Ensure the Test Runner points to the configured Scheduling service on the same local machine. Open the **Test Studio Test Runner** from the System Tray (it is started with Test Studio, or automatically on startup of the system, if the respective option is set).

![Test Runner System tray][3a]

Ensure the *Scheduling URL* is pointing to the local machine - *localhost* will be resolved to the absolute name of the machine.

![Test Runner][3]

## Setting Up a Project for Remote Scheduled Runs

1.&nbsp; Open the project which contains the <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> you wish to schedule for execution.

2.&nbsp; Under the *Project* tab click the **Connect** option in the *Scheduling* section of the ribbon.

![Connect][4]

3.&nbsp; In the **Scheduling Server Settings** dialog, click **Run Remotely**, input the location of your Scheduling Server, then click **Connect**. In the case you installed on components on a single machine, it is that local machine.

![Run Remotely][5]

## Schedule a Test List

<a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. You will be able to choose between the connected Execution machines.

## View Results of Remote Scheduled Run

<a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test list run is finished.

<p id=ports></p>
> Important: If the machines in your configuration have active firewalls, ensure that the following ports are opened in both in- and outbound directions on the respective machines:

> - Scheduling Service: 8009
> - Storage Service: 8492
> - Execution Machine(s): 55555

[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[2a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2a.png
[6]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig6.png
[3]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3.png
[3a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3a.png
[4]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[5]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png

[11]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[12]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[13]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png
[13a]: /img/features/scheduling-test-runs/create-scheduling-server/fig5a.png