---
title: Remote Scheduled Execution (Single Machine Setup)
page_title: Remote Scheduled Execution
description: "Test Studio can be configured to run tests and test lists on remote execution machines. Scheduling setup. Telerik Scheduling Storage service"
position: 3
---
# Remote Scheduled Execution (Single Machine Setup)

With Test Studio you can schedule test lists on a single machine, but using the Test Studio services and simulating remote test list execution. The Scheduling service setup allows you to keep the generated results in a storage database.

The below article describes how to enable scheduling tests for a Standalone Test Studio installation on a single machine. You can also __read this Step-By-Step series <a href="https://www.telerik.com/blogs/test-studio-step-by-step-scheduling-tests" target="_blank">blog post about setting up Test Studio Scheduling</a>__.

* [Installing Test Studio for Remote Scheduled Execution](#installing-test-studio-for-remote-scheduled-execution)
* [Configure the Test Studio Services](#configure-the-test-studio-services)
* [Configure the Execution Client](#configure-the-execution-client)
* [Setting Up a Project for Remote Scheduled Runs](#setting-up-a-project-for-remote-scheduled-runs)
* [Schedule a Test List](#schedule-a-test-list)
* [View Results of Remote Scheduled Run](#view-results-of-remote-scheduled-run)

## Installing Test Studio for Remote Scheduled Execution

Install Test Studio product and ensure to <a href="/getting-started/installation/install-procedure" target="_blank">include the Test Studio Scheduling Service and Storage Service components</a> in the **Customize Installation dialog**.

> **Note**
> <br>
> <br>
> The Test Studio services can be also added by <a href="/general-information/installation/add-services" target="_blank">changing the already installed product</a>.

![Installation Dialog][1]

> **Note**
> <br>
> <br>
> The **Storage service** uses <a href="https://www.mongodb.com/" target="_blank">**MongoDB**</a> as a storage database. The Test Studio installation wizard automatically detects, if there is an existing installation of the third party tool and if not, it will be additionally installed.

## Configure the Test Studio Services

Open Test Studio and under the *Project* tab in the *Scheduling* section, click **Configure** button in order to access the Test Studio Scheduling Config wizard.

![Configure][2]

Optionally, the **Configure Scheduling** wizard can be accessed through the Windows Start menu by typing *Configure Test Studio Services*.

![Configure scheduling setup wizard][2a]

Go through each tab to setup the Test Studio services:

- [MongoDB Tab](#mongodb-tab)
- [Storage Tab](#storage-tab)
- [Scheduling Tab](#scheduling-tab)
- [Setup Automatic Emails for Scheduled Jobs](#automatic-email-for-scheduled-test-lists)
- [Executive Dashboard Tab](#executive-dashboard-tab)

### MongoDB Tab

In the dialog which appears, the first **MongoDB** tab contains the settings required for the Mongo database. The **MongoDB data path** and **mongod.exe path** fields are populated with the values for a default MongoDB installation. Hit the **Apply** button and confirm the *MongoDB is started* status appears in the lower left corner of the wizard.

![MongoDB][11]

> **Note**
> <br>
> <br>
> The Scheduling config wizard uses the default MongoDB parameters to connect to it. Thus, you may need to change these, **only if the MongoDB installation was modified**.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Storage Tab

The **Storage** tab displays the Test Studio Storage service details - you can verify the **MongoDB connection string**, which is the default way to connect to the Mongo database. Hit the **Apply** button and check the *Telerik Storage Service is started* status appears in the lower left corner of the wizard.

![Storage][12]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Scheduling Tab

The **Scheduling** tab contains information about the location of the Test Studio Storage and Scheduling services. The default populated values are pointing to the local machine - *localhost*. For this particular configuration, these can remain unchanged and you can hit the **Apply** button. That will start the scheduling service and show you details about the storage service's status and database version in the **Storage Service Location** section. You will also see a message in the lower left corner of the wizard stating *'Telerik Scheduling Service is running'*.

![Scheduling][13]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Automatic Email for Scheduled Test Lists

Optionally, you can configure the Test Studio Scheduling service to use an Email (SMTP) server by specifying few additional details. These settings allow you to <a href="/features/scheduling-test-runs/schedule-execution#step-3" target="_blank">send an automatic email</a> with the results of a scheduled test list. Depending on the SMTP server configuration, mandatory fields are the *'SMTP server address'* and the *'Port'* to communicate with it and the *'User Email'* and *'Password'* are not explicitly required. Once these fields are populated, hit the **Apply** button to reflect the changes to the Scheduling service and check if the *'Telerik Scheduling Service is running'* appears in the lower left corner of the wizard.

![Scheduling SMTP][13a]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Executive Dashboard Tab

The <a href="/general-information/test-results/executive-dashboard" target="_blank">**Executive Dashboard** tab</a> contains information about the Storage service location used to get scheduled results from, and links the URL on which the Dashboard is hosted. The default populated values are pointing to the local machine - *localhost*. For this particular configuration, these can remain unchanged and you can hit the **Apply** button. This will start the Executive Dashboard service - you will see a in the lower left corner of the wizard stating *'Telerik Test Studio Executive Dashboard Service is running'*.

![Executive Dashboard][14]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

## Configure the Execution Client

Ensure the Test Runner points to the configured Scheduling service on the same local machine. Open the **Test Studio Test Runner** from the System Tray (it is started with Test Studio, or automatically on startup of the system, if the respective option is set).

![Test Runner System tray][3a]

Ensure the *Scheduling URL* is pointing to the local machine - *localhost* will be resolved to the absolute name of the machine.

![Test Runner][3]

## Setting Up a Project for Remote Scheduled Runs

Open a project, which contains the test list you wish to schedule for execution, and <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connect it to the configured Scheduler</a>. Under the *Project* tab click the **Connect** option in the *Scheduling* section of the ribbon.

![Connect][4]

In the **Scheduling Server Settings** dialog, click **Run Remotely**, input *localhost* (or use the name of the machine directly), then click **Connect**.

![Run Remotely][5]

## Schedule a Test List

<a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. You will be able to choose between the connected Execution machines.

## View Results of Remote Scheduled Run

<a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test list run is finished.

> __Important__
> <br>
> <br>
> If the machine has active firewall, ensure that the following ports are opened in both the inbound and outbound directions:
> - Scheduling Service: 8009
> - Storage Service: 8492
> - Execution Machine(s): 55555

## See Also

* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-scheduling-tests" target="_blank">Test Studio Step-by-Step: Scheduling Tests</a>

[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[2a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2a.png
[3]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3.png
[4]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[5]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png
[6]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig6.png
[11]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[12]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[13]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png
[13a]: /img/features/scheduling-test-runs/create-scheduling-server/fig5a.png
[14]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png

[3a]: /img/features/scheduling-test-runs/local-run-all-in-one/fig1.png
