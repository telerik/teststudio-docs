---
title: Schedule Execution
page_title: Schedule Test List Execution
description: "Test Studio test list schedule execution. How to schedule a test list on remote machine with Test Studio"
position: 9

---
# Schedule Test List Execution

Once you have <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured your Scheduling setup</a> with at least one execution machine connected and your current <a href="/features/scheduling-test-runs/connect-to-scheduling-server#schedule-tests-on-remote-execution-machines" target="_blank">project is connected to the Scheduling service</a>, you can proceed with scheduling test lists remotely.

This article guides you trough the below topics:

- [Schedule a test list](#scheduling-test-list-steps)
- [Scheduled job details](#scheduled-job-information)

## Scheduling Test List Steps

Once you have created a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a>, you can schedule it for execution at any time in the future. Initiate the _Scheduling wizard_ from the **Schedule TestList** button in the **Test List** tab.

![Schedule Test List](/img/features/scheduling-test-runs/schedule-execution/fig1.png)

Go through the steps to setup the scheduled job: 

- [Step 1 - Define start time and (optionally) job recurrence](#step-1)
- [Step 2 - Select execution machine(s) and (aoptionally) type of run](#step-2)
- [(Optional) Step 3 - Enable automatic email report for current scheduled job](#step-3)

### **Step 1**

Select the desired time and recurrence settings for this test run. In product version **R3 2015** we've introduced the ability to schedule test lists *Minutely* and *Hourly*.

![Step1](/img/features/scheduling-test-runs/schedule-execution/fig2.png)

### **Step 2**

Select Machine(s) step lets you pick the Execution Server on which to run the test list. If the list is empty, add at least one Execution Server. Picking multiple servers will result in the Test List executing simultaneously on all selected machines.

![Step2](/img/features/scheduling-test-runs/schedule-execution/fig3.png)

Options available:

- **Distribute tests among these machines** - Test Studio will split up the test list and assign each test to a different machine automatically. Note: If this setting is not selected, each test will run once on each machine you select, which may result in multiple test results for each test in the list.

- **Get latest version of tests automatically from TFS** - available only if the project is <a href="/features/source-control/tfs/connect-to-tfs" target="_blank">connected to a TFS</a>. If checked - Test Studio will perform a "check out" operation on the project latest version at each execution machine before running the test list.

> **Important**
> <br>
> <br>
> Test Studio ignores time zone differences and completely disregards the date and time on the Execution Server(s). The only date and time taken into account is on the machine where the Scheduling Server is located. This can lead to problems when the Scheduling Server is not located on the machine you're scheduling from and there are time zone differences between the two machines.

### **Step 3**

> **Note**
> <br>
> <br>
> This step is optional. To enable the option for sending automatic email for a scheduled job, you need to define the SMTP server and credentials in the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#automatic-email-notification-for-scheduled-executions" target="_blank">Scheduling Server Configuration wizard</a>Without these SMTP settings, _Step 3_ screen is not present.

Choose whether an automatic email is sent after test list completion and on what condition. [Read here additional details for email customization options](#email-notification-customization).

![Step3](/img/features/scheduling-test-runs/schedule-execution/fig4.png)

## Scheduled Job Information

Once you close the Scheduling Wizard, the scheduled run appears in the **Results** tab. It is yellow, indicating it's waiting to be executed.

![Results tab](/img/features/scheduling-test-runs/schedule-execution/fig10.png)

To remove a scheduled test execution:

- In the **Results** tab, hover over the scheduled test execution. Click the close button that appears.

![Close X ](/img/features/scheduling-test-runs/schedule-execution/fig11.png)

- If the scheduled test run is recurring, select whether to delete all instances or edit the scheduled run to remove specific test runs.

![Delete Series](/img/features/scheduling-test-runs/schedule-execution/fig12.png)

### Email Notification Customization

These steps lets you configure the e-mail notification sent upon test list completion.

![Select Notification Setting](/img/features/scheduling-test-runs/schedule-execution/fig5.png)

To disable mail notification, check __"I'm good...no mail for me!"__.

<br/>
If you check __"Send test results by email"__ select one of these three options:

- **Always** - receive a notification no matter what the result, pass or fail.

- **Only on execution errors (related to the app)** - sends an email only if a "normal" error is encountered. (For example, an error that's related to the application under test such as missing controls, wrong text values, etc.)

Under **Email Customization** customize the recipients, subject line, content, and attachments. Select the body content and attachments by checking the appropriate checkboxes.

![Email Customization](/img/features/scheduling-test-runs/schedule-execution/fig6.png)

Under __Subject Line__, type "//" to invoke the token field menu and include data from the test results in the subject line.

![Subject Line](/img/features/scheduling-test-runs/schedule-execution/fig7.png)

> __Note!__ Once you define a scheduled test list and enable the email message, all selected settings persist in that dialog next time you schedule a job within the same project.

To view the resulting email format, see the email preview on the right.

![Email Preview](/img/features/scheduling-test-runs/schedule-execution/fig8.png)

To further customize the email notification, click the **Edit** button and input custom text into the email template.

![Edit Template](/img/features/scheduling-test-runs/schedule-execution/fig9.png)

