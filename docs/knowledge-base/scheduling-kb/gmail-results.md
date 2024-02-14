---
title: Results Through Gmail
page_title: Results Through Gmail
description: Use Gmail SMTP Server to Send Result Email for Scheduled Test List Execution
position: 9
---
#Use Gmail SMTP Server to Send Result Email for Scheduled Test List Execution#

Test Studio's Scheduling feature allows you to send an email containing results from your test lists. However, in order to do so you'll need access to an SMTP server as well as the necessary rights to use it. You can view additional information on how to configure the SMTP settings <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">here</a>.

There's an alternative to using your company's SMTP server, however. You can use Gmail as the SMTP server for free. This is a great alternative to using a dedicated SMTP server. <a href="https://support.google.com/mail/troubleshooter/1668960?rd=1" target="_blank">This article</a> describes how to set this up. All you need is an active Gmail account.
 
Note: Ensure your company's security settings allow for communication with an SMTP server outside of the company's domain. This may not be allowed by default. Discuss this with your System Administrators.

In the context of Test Studio, here's how to make this work:

1. Start the **Configure as Scheduling Server** application.

2. Fill the Host **Name/IP** and **Port** fields and click the **Connect** button.

3. After you get the notification Connection Successful, click OK

4. Expand the **Configure Email (SMTP) Server** section.

5. Use the following settings and click **Done**:

**Address**: smtp.gmail.com

**Port**: 587

**User Email**: your gmail e-mail account

**Password**: the password for your gmail account


![SMTP configuration][1]

[1]: /img/knowledge-base/scheduling-kb/gmail-results/fig1.jpg