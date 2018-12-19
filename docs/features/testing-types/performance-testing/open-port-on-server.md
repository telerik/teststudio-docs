---
title: Open Port on Server
page_title: Open Port on Server
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
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



