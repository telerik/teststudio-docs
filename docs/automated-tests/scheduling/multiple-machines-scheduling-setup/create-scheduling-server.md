---
title: Configure Test Studio Services
page_title: Configure Test Studio Services
description: "Create a Scheduling Server in Test Studio to be able to run scheduled tests on remote machines. How to configure the Test Studio services in the Scheduling config wizard. The Telerik scheduling service keeps track of what tests to run and sends this data to the execution servers. This is a centralized component to control the scheduled test list runs in the Test Studio Scheduling setup"
position: 1
---
# Configure the Scheduling Services

The Test Studio Scheduling services work together to ensure the seamless communication between the project and machines, which execute the tests. Their configuration is related and, thus, performed in a single config wizard.

The below article describes the configuration steps.

- [Start the Test Studio Scheduling Config Wizard](#start-the-test-studio-scheduling-config-wizard)
- [Configure the Test Studio Services](#configure-the-test-studio-services)
- [Finish the Test Studio Services Configuration](#finish-the-test-studio-services-configuration)

> __Important__
> <br>
> <br>
> The Test Studio Services must be configured from a Windows Administrator account.

## Start the Test Studio Scheduling Config Wizard

You can start the Scheduling config wizard in any of the following ways:

* The  wizard can be accessed through the Windows Start menu by typing *Configure Test Studio Services*.

    ![Configure scheduling setup wizard][12a]

* The **Configure Test Studio Services** can be accessed through the opened in Test Studio project - click **Configure** button under the *Project* tab in the *Scheduling* section.

    ![Configure][12]

* Once Test Studio services get installed (no matter in which edition of the product), the installation wizard suggests to start the **Configure Test Studio Services** automatically.

    ![Start scheduling setup wizard after installation of services][1]

## Configure the Test Studio Services

> __Important__
> <br>
> <br>
> If the machines have active firewall, ensure that the following ports are opened in both the inbound and outbound directions for all machines used in the configuration:
> - Scheduling Service: 8009
> - Storage Service: 8492
> - Execution Machine(s): 55555

There are few tabs in the __Scheduling configuration wizard__, which provide the configuration details for each of the components of the Scheduling setup.

- [Communication Tab](#communication-tab)
- [MongoDB Tab](#mongodb-tab)
- [Storage Tab](#storage-tab)
- [Scheduling Tab](#scheduling-tab)
- [Setup Automatic Emails for Scheduled Jobs](#automatic-email-notification-for-scheduled-executions)
- [Executive Dashboard Tab](#executive-dashboard-tab)
- [Non Admin Port Setup Tab](#non-admin-port-setup-tab)

### Communication Tab 

The **Communication Key** is required by all Test Studio Scheduling components - services and clients, to establish the connection and communicate between each other. The **Communication** tab lets you manage the current key in use or generate and import a new one. 

![Communication tab][10]

The **Current Key** section allows you to **Copy to Clipboard** the current key in use or **Show** its value (for the cases when copying is not an option). 

The **Replace Key** section lets you **Generate** a new key. Once generated, the new value is populated in the text field and is ready to be imported. Hit the **Import** button to replace the current key with the new one. 

> **Note**
> <br>
> <br>
> Importing a new key in the Scheduling Config wizard **restarts the Scheduling service and Execution Server on that same machine to apply the new value**. 
> <br>
> <br>
> If Test Studio application is also running on the same machine at the time of renewing the communication key, it is not automatically restarted. To apply the recent changes you __need to restart the standalone Test Studio app manually__. 
><br> 
><br>
> See <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here step-by-step instructions on updating the communication key</a>.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### MongoDB Tab

The first tab is the **MongoDB** one and it contains the details required for the MongoDB database, which is used as a storage database in the Scheduling configuration.

The **MongoDB data path** and **mongod.exe path** fields are populated with the values for a default MongoDB installation, so you need to change these, **only if the MongoDB installation was modified**.

Hit the **Apply** button and confirm the *'MongoDB is running'* status appears in the lower left corner of the wizard.

![MongoDB][2]

> **Note**
> <br>
> <br>
> The **MongoDB** tab will be grayed out (inactive) if you do not have MongoDB installed on the machine! This will get enabled when the correct __Storage Service Location__ is set in the **Scheduling** tab.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Storage Tab

The **Storage** tab displays the connection details used from Test Studio Storage Service to access the MongoDB. The listed **MongoDB connection string** is the default connection string to be used for MongoDB database and is the only valid connection option for the Storage service.

Hit the **Apply** button and check the *'Telerik Storage Service is started'* status appears in the lower left corner of the wizard.

![Storage][3]

> **Note**
> <br>
> <br>
> The **Test Studio Storage Service and MongoDB** require to be installed on the same machine.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Scheduling Tab

The **Scheduling** tab provides information about the location of the __Test Studio Storage and Scheduling services__. The default populated values point to the local machine - *'localhost'*.

Hit the **Apply** button and check the *'Telerik Scheduling Service is running'* status appears in the lower left corner of the wizard. Once started, the Scheduling service also shows details about the connected Storage service's status and database version in the **Storage Service Location** section.

![Scheduling][4]

> **Note**
> <br>
> <br>
> If the Test Studio services are hosted on different machines, you can enter the respective machine name or IP to configure these.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Automatic Email Notification for Scheduled Executions

Optionally, the **Test Studio Scheduling service can be configured to use an Email (SMTP) server** by specifying the email server connection details. By adding these settings you will be able to <a href="/features/scheduling-test-runs/schedule-execution#step-3" target="_blank">send an automatic email</a> with the results of a scheduled test list.

The SMTP server settings are listed in the expandable section __Configure Email (SMTP) server__ in the **Scheduling** tab. Mandatory fields are the *'SMTP server address'* and the *'Port'* to communicate with it, and the *'User Email'*, who sends the email. Depending on the SMTP server configuration, thr *'Password'* field and *'Ssl'* checkbox may not be explicitly required.

Once the necessary data is entered, hit the **Apply** button to reflect the changes to the Scheduling service and check if the status *'Telerik Scheduling Service is running'* appears in the lower left corner of the wizard.

![Scheduling SMTP][5a]

> **Note**
> <br>
> <br>
> If you are using an Outlook account with two-factor authentication enabled, you need to use an __Application password__ created for the SMTP configuration. See the response in <a href="https://learn.microsoft.com/en-us/answers/questions/602284/sending-email-with-smtp-while-two-factor-enable" target="_blank">this Microsoft forum post</a> for further details. 

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Executive Dashboard Tab

The __Executive Dashboard__ tab provides information about the __Storage Service Location__ from which the <a href="/general-information/test-results/executive-dashboard" target="_blank">Dashboard</a> takes results. The default populated value points to the local machine - *'localhost'*. If the Test Studio services are hosted on different machines, you can enter the respective machine name or IP where the Storage service is running.

The __Executive Dashboard__ section of the tab allows changing the port on which the locally hosted Dashboard page runs. From the hyperlink in this section you can load the Dashboard page in your default set browser.

Hit the **Apply** button and check the *'Telerik Scheduling Service is running'* status appears in the lower left corner of the wizard.

![Executive dashboard][6]

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

### Non Admin Port Setup Tab

The __Non Admin Port Setup__ tab allows registering the ports, used from the Test Studio Scheduling configuration, to be available for users with no admin permissions in the _'URL Access Control List'_ for the preselected user or group. The default listed group __'NT Authority\Authenticated Users'__ represents all authenticated users. It can be changed to whatever is applicable for your organization.

> **Note**
> <br>
> <br>
> The default ports for the Test Studio services are reserved during installation for the _'NT Authority\Authenticated Users'_ user group.

Hit the __Grant Access__ button to create reservation for the listed ports and an informational message appears to report the status of the action.

![Register ports for non admin users][7]

In the sample screenshot two of the ports are already reserved for the users in the listed group - in such case you see an `Error: 183. Cannot create a file, when that file already exists.` message to inform that the ports cannot be registered second time for the same user group.

> **Tip**
> <br>
> <br>
> The __Ports in Use__ section displays the ports configured in the previous tabs of the Scheduling setup wizard. If you need to change any of these, get back to the respective tab and apply the necessary changes.

<br>
<div><a style="float:right" href="#configure-the-test-studio-services">Back to top of section</a></div>
<br>

## Finish the Test Studio Services Configuration

When all necessary settings are applied and all services are reported running, close the wizard window to finish the Scheduling Services setup.


## See Also

* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-running-tests-remotely" target="_blank">Test Studio Step-by-Step: Running Tests Remotely</a>

[1]: /img/features/scheduling-test-runs/create-scheduling-server/fig1.png
[12]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2.png
[12a]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig2a.png
[2]: /img/features/scheduling-test-runs/create-scheduling-server/fig2new.png
[3]: /img/features/scheduling-test-runs/create-scheduling-server/fig3new.png
[4]: /img/features/scheduling-test-runs/create-scheduling-server/fig5new.png
[5a]: /img/features/scheduling-test-runs/create-scheduling-server/fig5a.png
[6]: /img/features/scheduling-test-runs/create-scheduling-server/fig4new.png
[7]: /img/features/scheduling-test-runs/create-scheduling-server/fig7.png
[10]: /img/features/scheduling-test-runs/create-scheduling-server/communication-tab.png