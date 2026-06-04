---
title: Configuration
page_title: Bug Tracking Configuration
description: "Configure bug tracker in Test Studio. Built-in bug tracker in Test Studio. Can I submit bug directly from Test Studio. Bug tracking system integration in Test Studio."
previous_url: /user-guide/extensions/bug-tracking/configuration.aspx, /user-guide/extensions/bug-tracking/configuration
position: 1
---
# Bug Tracking Configuration

Connect with bug tracking applications to track bugs you encounter while testing your application. Test Studio has integration with the TFS and Jira bug trackers and will log bugs directly into the configured defect tracking system. The bug tracking integration is pluggable and you also can <a href="/features/integration/bug-tracking/custom-plugin" target="_blank">build a plug-in</a> for your custom-made, in-house system.

- <a href="/features/integration/bug-tracking/configuration#team-foundation-server-and-azure-devops">TFS</a>
- <a href="/features/integration/bug-tracking/configuration#jira-server">Jira Server</a>
- <a href="/features/integration/bug-tracking/configuration#jira-cloud">Jira Cloud</a>

## Team Foundation Server and Azure DevOps

1. Click the Bug Tracking button under the *Extensions* section in the *Project* ribbon.

![Bug Tracking](/img/features/integration/bug-tracking/configuration/bug-report-icon-navigate.png)

2. The **Manage Bug Tracking** dialog appears, where the integrated systems are listed. Select the desired application and click the pencil ![Pencil](/img/features/integration/bug-tracking/configuration/fig2.png) to **Configure Selected**.

![Manage Bug Tracking](/img/features/integration/bug-tracking/configuration/bug-report-propt.png)

3. From the first dropdown select the tracker you will configure - on-premise TFS server or the online service currently named Azure DevOps.

![Bug Tracking Setup select TFS on-premise or online](/img/features/integration/bug-tracking/configuration/fig4.png)

4. Enter the Server URL and click the **Connect** button.

<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
		<td>
		
<img src="/img/features/integration/bug-tracking/configuration/fig5.png" alt="TFS service Online" /> <br><br>Azure DevOps (Online TFS Service)</td>
<td>
		
<img src="/img/features/integration/bug-tracking/configuration/fig6.png" alt="TFS server on premise" /> <br><br>TFS Server on-premise</td>
</tr>
</table>

Enter valid credentials when prompted. The below example requires username and password for the Azure DevOps service. 

![TFS Login](/img/features/integration/bug-tracking/configuration/fig7.png)

5. Once the connection to the server is successfully established, select the **Team Project** for Azure DevOps, and the **Team Project Collection** and **Team Project** for on-premise server, then click **Save**.

<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
		<td>

<img src="/img/features/integration/bug-tracking/configuration/fig8.png" alt="TFS service Online" /> <br><br>Azure DevOps (Online TFS Service)</td>
<td>
		
<img src="/img/features/integration/bug-tracking/configuration/fig9.png" alt="TFS server on premise" /> <br><br>TFS Server on-premise</td>
</tr>
</table>

## Jira Server

1. Click the Bug Tracking button under the *Extensions* section in the *Project* ribbon.

![Bug Tracking](/img/features/integration/bug-tracking/configuration/bug-report-icon-navigate.png)

2. The **Manage Bug Tracking** dialog appears, where the integrated systems are listed. Select the desired application and click the pencil ![Pencil](/img/features/integration/bug-tracking/configuration/fig2.png) to **Configure Selected**.

![Manage Bug Tracking](/img/features/integration/bug-tracking/configuration/bug-report-icon-navigate-JIRA.png)

3. Enter the Server URL, username and password and click the **Connect** button.

> The format of the server URL requires http://jiraserver.com (dashboard or other links that end on *.jspa are not accepted).

![Login to JIRA](/img/features/integration/bug-tracking/configuration/fig10.png)

4. Select your project and click **Save**.

![Login to JIRA Tracker](/img/features/integration/bug-tracking/configuration/fig11.png)

> The JIRA project schema should have a Bug item. The default schema of a new project does not contain such item and Test Studio would fail to submit a bug in that case.

> Please note that using **xxxx.jira.com** for connecting bug tracking to Test Studio requires HTTPS.

## Jira Cloud

1. Add the issue type **Bug** as an available issue type in your Jira Cloud administration panel.

![Issue Types](/img/features/integration/bug-tracking/configuration/fig13.jpg)

2. Your user must be a member of the “**jira-users**” group to  have permission to connect to Jira Cloud from Test Studio. You could also use the “admin” account. 

![Group Membership](/img/features/integration/bug-tracking/configuration/fig14.jpg)

3. Use the correct URL to connect to your Jira Cloud server.

![Bug tracking settings](/img/features/integration/bug-tracking/configuration/fig15.png)

4. Enter your Jira username and for a password use a <a href="https://id.atlassian.com/manage/api-tokens" target="_blank">Jira Token</a> generated for your account - that way Test Studio integration will successfully comply with the two-factor authentication for the Jira cloud server.

![Jira Login](/img/features/integration/bug-tracking/configuration/fig16.jpg)

## Set Default Configured Bug Tracker

The Bug Tracking applications are now properly configured. Select one to be the default and click **Save**.

![Manage Bug Tracking](/img/features/integration/bug-tracking/configuration/fig12.png)

## Advanced Settings

Click **Advanced Settings** ![Advanced settings button](/img/features/integration/bug-tracking/configuration/advanced-settings.png) to set whether to attach failure details and/or auto-submit.

* **Attach failure details** - Test Studio will include the bug information as an attachment. For example you will see the bug details as a File Attachment in TFS.

* **Auto-submit** - Everytime a test or step fails within a test list, Test Studio will automatically submit a bug for you. Please make sure that you've set up a default bug tracking tool.<br>

>**Note:** This is Test Studio **test list** execution feature only! It works for local and remote test list execution from Test Studio. It works also when test list is run through <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a> or through the scheduling command line client <a href="/features/scheduling-test-runs/tts-command-line-client" target="_blank">Telerik.TestStudio.CommandLineClient</a>.

![Bug Tracking Settings](/img/features/integration/bug-tracking/configuration/choose-advanced-settings.png)

