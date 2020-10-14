---
title: Change Scheduling Service Account
page_title: Change Scheduling Service Account
description: "Test Studio Scheduling Service Account. change the Scheduling Service Account if using TFS with different than the logged user account"
position: 1

---
# Scheduling service account

Due to restrictions in your network environment, or in order to <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">get latest from TFS automatically</a>, you may need to change the user account for the Scheduling Service. For more information about the correct user account for your Scheduling Service, contact your network administrator.

1.&nbsp; On the Scheduling Server machine, click **Control Panel > System and Security > Administrative Tools > Services**.

2.&nbsp; In the **Services** window, right-click the **Telerik Test Studio Scheduling Service** and click **Properties**.

![Services][1]

3.&nbsp; Open the **Log On** tab of the Properties dialog and update with the TFS account credentials for the Scheduling Service.

![Log On][2]

[1]: /img/features/scheduling-test-runs/change-service-account/fig1.png
[2]: /img/features/scheduling-test-runs/change-service-account/fig2.png
