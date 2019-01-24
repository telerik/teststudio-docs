---
title: Configuration
page_title: Bug Tracking Configuration
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/extensions/bug-tracking/configuration.aspx, /user-guide/extensions/bug-tracking/configuration
position: 1
---
# Bug Tracking Configuration

Connect with bug tracking applications to track bugs you encounter while testing your application. Test Studio has integration with the following bug trackers:

- <a href="#tfs">Team Foundation Server</a>
- <a href="#jira">JIRA</a>
- <a href="#jira-cloud">JIRA Cloud</a>

Log bugs directly from Test Studio into defect tracking systems like TeamPulse and Team Foundation Server. The bug tracking integration is pluggable, so you can build a plug-in for your custom-made, in-house system.

1.&nbsp; There are two ways to launch Bug Tracking on the Project tab:

- Click the Bug Tracking button in the Extensions ribbon.

![Bug Tracking][1]

2.&nbsp; The **Manage Bug Tracking** dialog appears <a name="tfs"></a>. Select an application and click **Configure Selected** ![Pencil][2]. The following steps are for TFS. For **TeamPulse**, skip to step 6. For **Jira**, skip to step 7.

![Manage Bug Tracking][3]

- Click **Advanced Settings** ![Advanced settings button][4] to set whether to attach failure details and auto-submit.

	*	**Attach failure details** - Test Studio will include the bug information as an attachment. For example you will see the bug details as a File Attachment in TFS.

	*	**Auto-submit** - Everytime a test or step fails within a test list, Test Studio will automatically submit a bug for you. Please make sure that you've set up a default bug tracking tool.<br>
	
	**Note:** This is Test Studio **test list** execution feature only! It works for local and remote test list execution from Test Studio. It works also when test list is run through <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a> or through the scheduling command line client <a href="/features/scheduling-test-runs/tts-command-line-client" target="_blank">Telerik.TestStudio.CommandLineClient</a>.

![Bug Tracking Settings][5]

3.&nbsp; If you have previously configured Bug Tracking Settings through the <a href="/features/testing-types/exploratory-testing/overview" target="_blank">Exploratory Tool</a>, you can choose to import those settings.

![Import Bug Tracking Settings][6]

4.&nbsp; Enter the Server URL, Username, Password, and click **Connect**.

![Bug Tracking Setup][7]

5.&nbsp; Under the **TFS Project Details** section, select the **Team Project Collection** and **Team Project**, then click **Save**. Skip to step 9.

![TFS Trackers][8]

6.&nbsp; Enter the Server URL, Username, Password, and click **Connect** <a name="jira"></a>.

![Login to JIRA][10]

> The format of the server URL requires http://jiraserver.com (dashboard or other links that end on *.jspa are not accepted).

7.&nbsp; Select your project and click **Save**.

![Login to JIRA Tracker][11]

> The JIRA project schema should have a Bug item. The default schema of a new project does not contain such item and Test Studio would fail to submit a bug in that case.

> Please note that using **xxxx.jira.com** for connecting bug tracking to Test Studio requires HTTPS. 

##Jira Cloud

1.&nbsp; Add the issue type **Bug** as an available issue type in your Jira Cloud administration panel.

![Issue Types][13]

2.&nbsp; Your user must be a member of the “**jira-users**” group to  have permission to connect to Jira Cloud from Test Studio. You could also use the “admin” account. 

![Group Membership][14]

3.&nbsp; Use the correct URL to connect to your Jira Account.

![Bug tracking settings][15]

4.&nbsp; You should enter the same username and password as you would use to log in to your Jira Cloud account

![Jira Login][16]

The Bug Tracking applications are now properly configured. Select one to be the default and click **Save**.

![Manage Bug Tracking][12]


[1]: /img/features/integration/bug-tracking/configuration/fig1.png
[2]: /img/features/integration/bug-tracking/configuration/fig2.png
[3]: /img/features/integration/bug-tracking/configuration/fig3.png
[4]: /img/features/integration/bug-tracking/configuration/fig4.png
[5]: /img/features/integration/bug-tracking/configuration/fig5.png
[6]: /img/features/integration/bug-tracking/configuration/fig6.png
[7]: /img/features/integration/bug-tracking/configuration/fig7.png
[8]: /img/features/integration/bug-tracking/configuration/fig8.png
[9]: /img/features/integration/bug-tracking/configuration/fig9.png
[10]: /img/features/integration/bug-tracking/configuration/fig10.png
[11]: /img/features/integration/bug-tracking/configuration/fig11.png
[12]: /img/features/integration/bug-tracking/configuration/fig12.png
[13]: /img/features/integration/bug-tracking/configuration/fig13.jpg
[14]: /img/features/integration/bug-tracking/configuration/fig14.jpg
[15]: /img/features/integration/bug-tracking/configuration/fig15.jpg
[16]: /img/features/integration/bug-tracking/configuration/fig16.jpg


