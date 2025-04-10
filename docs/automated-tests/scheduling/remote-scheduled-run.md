---
title: Remote Scheduled Execution (Single Machine Setup)
page_title: Remote Scheduled Execution
description: "Test Studio can be configured to run tests and test lists on remote execution machines. Scheduling setup. Telerik Scheduling Storage service"
position: 3
---
# Remote Scheduled Execution (Single Machine Setup)

With Test Studio you can schedule test lists on a single machine, but using the Test Studio services and simulating remote test list execution. The Scheduling service setup allows you to keep the generated results in a storage database.

The below article describes how to enable scheduling tests for a Standalone Test Studio installation on a single machine. 

> **Tip**
> <br>
> <br>
> You refer to __this Step-By-Step <a href="https://www.telerik.com/blogs/test-studio-step-by-step-scheduling-tests" target="_blank">blog post about setting up Test Studio Scheduling</a>__.

<!-- no toc -->
- [Remote Scheduled Execution (Single Machine Setup)](#remote-scheduled-execution-single-machine-setup)
  - [Installing Test Studio for Remote Scheduled Execution](#installing-test-studio-for-remote-scheduled-execution)
  - [Configure the Test Studio Services](#configure-the-test-studio-services)
    - [Communication Tab](#communication-tab)
    - [MongoDB Tab](#mongodb-tab)
    - [Storage Tab](#storage-tab)
    - [Scheduling Tab](#scheduling-tab)
    - [Automatic Email for Scheduled Test Lists](#automatic-email-for-scheduled-test-lists)
    - [Executive Dashboard Tab](#executive-dashboard-tab)
    - [Execution Server Tab](#execution-server-tab)
  - [Configure the Execution Client](#configure-the-execution-client)
  - [Setting Up a Project for Remote Scheduled Runs](#setting-up-a-project-for-remote-scheduled-runs)
  - [Schedule a Test List](#schedule-a-test-list)
  - [View Results of Remote Scheduled Run](#view-results-of-remote-scheduled-run)

    

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
> The **Storage service** uses <a href="https://www.mongodb.com/" target="_blank">**MongoDB**</a> as a storage database. The Test Studio installation wizard automatically detects if an existing installation of the third party tool is present. If MongoDB is not installed the installation wizard initiates the additional installation automatically.

## Configure the Test Studio Services

> __Important__
> <br>
> <br>
> If the machine has active firewall, ensure that the following ports are opened in both the inbound and outbound directions:
> - Scheduling Service: 8009
> - Storage Service: 8492
> - Execution Machine(s): 55555

Open a Test Studio project and select **Configure** button under the **Project** -> **Scheduling** ribbon and wait for the Test Studio Scheduling Config wizard to get opened.

![Configure scheduling setup button][2]

Optionally, the **Configure Services** wizard can be accessed through the Windows Start menu by typing *Configure Test Studio Services*.

![Configure Test Studio services][2a]

Go through each tab to setup the Test Studio services:
<!-- no toc -->
  * [Communication Tab](#communication-tab)
  * [MongoDB Tab](#mongodb-tab)
  * [Storage Tab](#storage-tab)
  * [Scheduling Tab](#scheduling-tab)
  * [Automatic Email for Scheduled Test Lists](#automatic-email-for-scheduled-test-lists)
  * [Executive Dashboard Tab](#executive-dashboard-tab)
  * [Execution Server Tab](#execution-server-tab)


### Communication Tab 

The Communication tab lets you manage the **Communication Key** which is required by all Test Studio Scheduling components - services and clients. It is used to establish the connection and successful communication between each of the Scheduling modules. 

![Communication tab][10]

The **Current Key** section indicates which is the key in use. The Scheduling setup is configured to use a default communication key for each Test Studio installation. Thus, after initial install you see the current key is the __Default Key Loaded__. In this configuration you can't copy or see the key. 

![Default Communication key][101]

> **Tip**
> <br>
> <br>
> We strongly recommend to generate a new custom communication key and replace it for all machines in the setup.
><br>
> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.

Once a custom key is generated and imported, the **Current Key** section allows you to copy the value of the key using the __Copy to Clipboard__ button, or see it using the __Show__ button (for the cases when copying is not an option). The key value can be reset to the default value using the __Reset to Default__ button.

![Custom Communication key][102]

The **Replace Key** section lets you **Generate** a new key. Once generated, the new value is populated in the text field and is ready to be imported. Hit the **Import** button to replace the current key with the new one. 

![Replace Communication key][103]

> **Note**
> <br>
> <br>
> Importing a new key in the Scheduling Config wizard **restarts the Scheduling service on that same machine to apply the new value**. 
> <br>
> <br>
> The Execution Client application is stopped but you need to start it manually. 
> If Test Studio application is also running on the same machine at the time of renewing the communication key, it is not automatically restarted. To apply the recent changes you __need to restart the standalone Test Studio app manually__. 
><br> 
><br>
> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### MongoDB Tab

The **MongoDB** tab contains the details required for the MongoDB database, which is used as a storage database in the Scheduling configuration.

The **MongoDB data path** and **mongod.exe path** fields are populated with the values for a default MongoDB installation, so you need to change these, **only if the MongoDB installation was modified**.

Hit the **Apply** button and confirm the *'MongoDB is running'* status appears in the lower left corner of the wizard.

![MongoDB][11]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Storage Tab

The **Storage** tab displays the connection details used from Test Studio Storage Service to access the MongoDB. The listed **MongoDB connection string** is the default connection string to be used for MongoDB database and is the only valid connection option for the Storage service.

Hit the **Apply** button and check the *'Telerik Storage Service is started'* status appears in the lower left corner of the wizard.

![Storage][12]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Scheduling Tab

The **Scheduling** tab contains information about the location of the Test Studio Storage and Scheduling services. The default populated values are pointing to the local machine - *localhost*. 

For this particular configuration, these can remain unchanged and you can hit the **Apply** button. This starts the scheduling service which is indicated with a message in the lower left corner of the wizard stating *'Telerik Scheduling Service is running'*.

![Scheduling][13]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Automatic Email for Scheduled Test Lists

Optionally, you can configure the Test Studio Scheduling service to use an Email (SMTP) server by specifying few additional details. These settings allow you to <a href="/features/scheduling-test-runs/schedule-execution#step-3" target="_blank">send an automatic email</a> with the results of a scheduled test list. 

The SMTP server settings are listed in the expandable section __Configure Email (SMTP) server__ in the **Scheduling** tab. Mandatory fields are the **'SMTP server address'** and the **'Port'** to communicate with it, and the **'User Email'**, who sends the email. Depending on the SMTP server configuration, the **'Password'** field and **'Ssl'** checkbox may not be explicitly required.

Once the necessary data is entered, hit the **Apply** button to reflect the changes to the Scheduling service and check if the status *'Telerik Scheduling Service is running'* appears in the lower left corner of the wizard.

![Scheduling SMTP][13a]

> **Note**
> <br>
> <br>
> If you are using an Outlook account with two-factor authentication enabled, you need to use an __Application password__ created for the SMTP configuration. See the response in <a href="https://learn.microsoft.com/en-us/answers/questions/602284/sending-email-with-smtp-while-two-factor-enable" target="_blank">this Microsoft forum post</a> for further details. 

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Executive Dashboard Tab

The <a href="/general-information/test-results/executive-dashboard" target="_blank">**Executive Dashboard** tab</a> contains information about the Storage service location used to get scheduled results from, and links the URL on which the Dashboard is hosted. The default populated values point to the local machine - *localhost*. 

For this particular configuration, these can remain unchanged and you can hit the **Apply** button. This will start the Executive Dashboard service - you will see a message in the lower left corner of the wizard stating *'Telerik Test Studio Executive Dashboard Service is running'*.

![Executive Dashboard][14]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Execution Server Tab

The __Execution Server__ tab contains information for the configuration settings of the Execution client application. In this tab you can change the Scheduling URL to which the Execution client is connected, the port and temp folder it uses, and whether to run it on startup. 
 
The default populated values point to the local machine Scheduling service - _localhost_ using the port 55555. Hit the __Apply__ button to apply any changes - wait until you see a message in the lower left corner of the wizard stating _'Changes applied successfully'_.

![Execution Server config tab][15]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

## Configure the Execution Client

Open the **Test Studio Test Runner** from the System Tray (it is started with Test Studio, or automatically on startup of the system, if the respective option is set).

![Test Runner System tray][30]

Use the __Configure__ button If you need to change anything in the configuration of the Execution Server. It opens up the Scheduling config wizard on its [__Execution Server__ tab](#execution-server-tab).

![Test Runner Config button][33]

Ensure the **Scheduling URL** points to the local machine - *localhost* will be resolved to the absolute name of the machine. 

![Test Runner Scheduling URL][3]

The communication **Key** is required to establish the connection and to enable the communication to the Scheduling server. A <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-services" target="_blank">key is generated in the Scheduling Config wizard</a> and if it's not matching on both the Scheduler and Execution machines, the connection between these is not possible. 

![Test Runner Communication key][3a]

> **Note**
><br> 
><br> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.



## Setting Up a Project for Remote Scheduled Runs

Open the Test Studio project which contains the test list to schedule for unattended execution and click the **Connect** button from the `Scheduling` ribbon in the **Project** tab.

![Connect Project][4]

In the **Scheduling Server Settings** dialog, choose **Remote** radio button to connect the project to the configured Scheduling server. Enter the Scheduling machine name or, for the current setup, use *localhost* and click the **Connect** button.

![Connect to Scheduling machine][5]

A confirmation message appears when the connection is successful. Confirm the connection by pressing the __Confirm__ button in the dialog. 

## Schedule a Test List

<a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule Test List execution</a> in the Test Lists view. You will be able to choose between the connected Execution machines.

## View Results of Remote Scheduled Run

<a href="/features/scheduling-test-runs/scheduling-results" target="_blank">View Scheduling Results</a> after the scheduled test list run is finished.



## See Also

* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-scheduling-tests" target="_blank">Test Studio Step-by-Step: Scheduling Tests</a>

[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig1.png
[2]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[2a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2a.png
[3]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3.png
[3a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig3a.png
[33]: /img/features/scheduling-test-runs/remote-run-all-in-one/configure-execution-server-button.png
[4]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[5]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig5.png
[10]: /img/features/scheduling-test-runs/create-scheduling-server/communication-tab.png
[101]: /img/features/scheduling-test-runs/create-scheduling-server/communication-tab-default-key.png
[102]: /img/features/scheduling-test-runs/create-scheduling-server/communication-tab-custom-key.png
[103]: /img/features/scheduling-test-runs/create-scheduling-server/communication-tab-replace-key.png
[11]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[12]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[13]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png
[13a]: /img/features/scheduling-test-runs/create-scheduling-server/fig5a.png
[14]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png
[15]: /img/features/scheduling-test-runs/create-scheduling-server/execution-client-tab.png
[30]: /img/features/scheduling-test-runs/local-run-all-in-one/fig1.png
