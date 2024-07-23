---
title: Results Through Gmail
page_title: Results Through Gmail
description: Use Gmail SMTP Server to Send Result Email for Scheduled Test List Execution
position: 9
---
# Use Gmail SMTP Server to Send Result Email for Scheduled Test List Execution 

Test Studio's Scheduling service allows sending an email with the results from scheduled test list runs. To enable the feature you need an available SMTP server and the necessary settings to access it from within Test Studio. 

This article describes the settings needed if you decide to use the Google SMTP server instead of a company mail server in the Test Studio Scheduling setup. 
 
> __Important__ 
> <br>
> Ensure your company's security settings allow for communication with an SMTP server outside of the company's domain. As this may not be allowed by default you may need to discuss the matter with your System Administrators.

## Prerequisites

You need to have few things in place before you continue: 

* Active gmail account;
* Two-factor authentication activated for the gmail account;
* An application password created for the gmail account - see <a href="https://support.google.com/accounts/answer/185833/" target="_blank">here for further details and recommendations on using an application password</a>. 

## Configure Google SMTP in Test Studio Scheduling Service

Follow the steps below to apply the settings for using the Google mail server. 

1. <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Start the Test Studio Scheduling Config Wizard application</a>. 

2. Switch to the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#scheduling-tab" target="_blank">Scheduling tab</a> in the wizard. 

3. Expand the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#automatic-email-notification-for-scheduled-executions" target="_blank">Configure Email (SMTP) Server section</a>.

4. Use the following settings for the gmail SMTP:

    **Address**: smtp.gmail.com

    **Port**: 587

    **User Email**: your gmail email account

    **Password**: the application password created for your gmail account

    **Ssl**: enable the checkbox

5. Use the **Apply** button to restart the Scheduling service and let it use the SMTP settings. 

    ![SMTP configuration][1]

[1]: /img/knowledge-base/scheduling-kb/gmail-results/fig1.png