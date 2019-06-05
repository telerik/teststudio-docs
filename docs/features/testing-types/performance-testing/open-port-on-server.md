---
title: Open Port on Server
page_title: Open Port on Server
description: "Open Port on Server for a performance test in Test Studio project."
previous_url: /user-guide/performance/open-port-on-server.aspx, /user-guide/performance/open-port-on-server
position: 2
---
# Open Port on Server

1.&nbsp; Click **Start > All Programs > Administrative Tools > Windows Firewall with Advanced Security**.

![Win firewall][1]

2.&nbsp; Select Inbound Rules.

![Inbound Rule][2]

3.&nbsp; Select **Action > New Rule**.

![New Rule][3]

4.&nbsp; Proceed with the New Inbound Rule Wizard and enter the following information:


- **Rule Type** = Port
- **Protocol and Ports** = TCP
  - **Specific port** = 8031
- **Action** = Allow the connection
- **Profile** = (leave all three checked)
- **Name** = Test Studio


[1]: /img/features/testing-types/performance-testing/open-port-on-server/fig1.png
[2]: /img/features/testing-types/performance-testing/open-port-on-server/fig2.png
[3]: /img/features/testing-types/performance-testing/open-port-on-server/fig3.png



