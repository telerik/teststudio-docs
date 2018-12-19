---
title: Schedule Execution
page_title: Schedule Test List Execution
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 9
previous_url: /user-guide/scheduling-test-runs/schedule-test-execution.aspx, /user-guide/scheduling-test-runs/schedule-test-execution
---
# Schedule Test List Execution

Once you've correctly <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">configured</a> a Scheduling Server and you've attached at least one <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution Server</a> to it, you can proceed with scheduling a test list run.

<br/>

## Scheduling Test List steps

Once you have a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a>, you can schedule it for execution. From **Test List** tab - click on **Schedule TestList** in the **Scheduling** ribbon.

![Schedule Test List][1]

### **Step 1**

Select the desired time and recurrence settings for this test run. In product version **R3 2015** we've introduced the ability to schedule test lists *Minutely* and *Hourly*. 

![Step1][2]

### **Step 2**

Select Machine(s) step lets you pick the Execution Server on which to run the test list. If the list is empty, add at least one Execution Server. Picking multiple servers will result in the Test List executing simultaneously on all selected machines. 

![Step2][3]

Options available:

- **Distribute tests among these machines** - Test Studio will split up the test list and assign each test to a different machine automatically. Note: If this setting is not selected, each test will run once on each machine you select, which may result in multiple test results for each test in the list.

- **Get latest version of tests automatically from TFS** - available only if the project is <a href="/features/source-control/tfs/connect-to-tfs" target="_blank">connected to a TFS</a>. If checked - Test Studio will perform a "check out" operation on the project latest version at each execution machine before running the test list.

> **Important** Test Studio ignores time zone differences and completely disregards the date and time on the Execution Server(s). The only date and time taken into account is on the machine where the Scheduling Server is located. This can lead to problems when the Scheduling Server is not located on the machine you're scheduling from and there are time zone differences between the two machines.

### **Step 3**

> This step is optional. Notifications are sent from the Scheduling Server and it needs the necessary permissions to use the SMTP server with credentials as configured in the <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">Create a Scheduling Server</a> section. Without these SMTP settings, Step 3 will be skipped.

Screenshot below shows all settings available for adjustment in the notification configuration step.

Further email customization information is available <a href="/features/scheduling-test-runs/schedule-execution#Email-notification-customization">here</a>.

![Step3][4]

<br/>

## Scheduled job information

Once you close the Scheduling Wizard, the scheduled run should appear in the **Results** tab. It should be yellow, indicating it's waiting to be executed.

![Results tab][10]

To remove a scheduled test execution:

- In the **Results** tab, hover over the scheduled test execution. Click the close button that appears.

![Close X ][11]

- If the scheduled test run is recurring, select whether to delete all instances or edit the scheduled run to remove specific test runs.

![Delete Series][12]

<br/>

## Automatically upload changed project files to Storage

As of release **2017 R3** (v.2017.3.1010) you could choose whether to automatically upload all recent changes to the storage database. The below dialog will be triggered after saving the project and if there are any upcoming scheduled test list runs within that project.

![Automatic Files Update][13]

If it is clear whether the automatic upload for that project is required or not and you don't want to see the notification by each save operation you could check the respective checkbox. The selected option will be applied on project level and performed automatically once the project is saved. Alternatively you could leave the prompt dialog to be triggered by each save operation and choose each time whether to upload the changes or not.

<br/>

## Email notification customization

These steps lets you configure the e-mail notification you will receive upon test list completion.

![Select Notification Setting][5]

To disable mail notification, check __"I'm good...no mail for me!"__.

<br/>
If you check __"Send test results by email"__ select one of these three options:

- **Always** - receive a notification no matter what the result, pass or fail.

- **Only on execution errors (related to the app)** - sends an email only if a "normal" error is encountered. (For example, an error that's related to the application under test such as missing controls, wrong text values, etc.)

Under **Email Customization** customize the recipients, subject line, content, and attachments. Select the body content and attachments by checking the appropriate checkboxes.

![Email Customization][6]

Under __Subject Line__, type "//" to invoke the token field menu and include data from the test results in the subject line.

![Subject Line][7]

> __Note:__ Once a test list is scheduled with any email settings applied, the selected settings will persist in that dialog next time a job is scheduled within the same project.

To view the resulting email format, see the email preview on the right.

![Email Preview][8]

To further customize the email notification, click the **Edit** button and input custom text into the email template.

![Edit Template][9]

[1]: /img/features/scheduling-test-runs/schedule-execution/fig1.png
[2]: /img/features/scheduling-test-runs/schedule-execution/fig2.png
[3]: /img/features/scheduling-test-runs/schedule-execution/fig3.png
[4]: /img/features/scheduling-test-runs/schedule-execution/fig4.png
[5]: /img/features/scheduling-test-runs/schedule-execution/fig5.png
[6]: /img/features/scheduling-test-runs/schedule-execution/fig6.png
[7]: /img/features/scheduling-test-runs/schedule-execution/fig7.png
[8]: /img/features/scheduling-test-runs/schedule-execution/fig8.png
[9]: /img/features/scheduling-test-runs/schedule-execution/fig9.png
[10]: /img/features/scheduling-test-runs/schedule-execution/fig10.png
[11]: /img/features/scheduling-test-runs/schedule-execution/fig11.png
[12]: /img/features/scheduling-test-runs/schedule-execution/fig12.png
[13]: /img/features/scheduling-test-runs/schedule-execution/fig13.png