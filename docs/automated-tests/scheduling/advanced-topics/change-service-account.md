---
title: Change Scheduling Service Account
page_title: Change Scheduling Service Account
description: "Test Studio Scheduling Service Account. change the Scheduling Service Account if using TFS with different than the logged user account, Get Latest from TFS for Test Studio Scheduled job fails to authenticate, Get Latest from TFS fails to authenticate for scheduled test list run in Test Studio"
position: 1
publish: false

---
# Scheduling service account

Once you have <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured your Scheduling setup</a> with at least one execution machine connected and your current <a href="/features/scheduling-test-runs/connect-to-scheduling-server#schedule-tests-on-remote-execution-machines" target="_blank">project is connected to the Scheduling service</a>, you can proceed with scheduling test lists remotely.

If you experience any connectivity issues, there might be certain restrictions in your network environment, which require a change to the account used to start the Scheduling service. This can be the usage of the option to <a href="/features/scheduling-test-runs/schedule-execution#step-2" target="_blank">get latest from TFS automatically</a> when scheduling a test list. For more information about the correct user account for your Scheduling Service, contact your network administrator.

## How to Change the Scheduling Service Account

1.&nbsp; On the Scheduling Server machine, click **Control Panel > System and Security > Administrative Tools > Services**.

2.&nbsp; In the **Services** window, right-click the **Telerik Test Studio Scheduling Service** and click **Properties**.

![Services][1]

3.&nbsp; Open the **Log On** tab of the Properties dialog and update with the TFS account credentials for the Scheduling Service.

![Log On][2]

[1]: /img/features/scheduling-test-runs/change-service-account/fig1.png
[2]: /img/features/scheduling-test-runs/change-service-account/fig2.png
