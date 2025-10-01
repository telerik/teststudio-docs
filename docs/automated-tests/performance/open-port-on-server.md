---
title: How to Open Port on Server
page_title: Performance Testing - Open Port on Server
description: "Open Port on Server for a performance test in Test Studio project."
position: 9
---
# Open Port on Server for Test Studio Performance Testing

You can use the <a href="/features/testing-types/performance-testing/overview" target="_blank">Test Studio performance testing</a> for profiling a remote server. For this you will need at minimum the <a href="https://www.telerik.com/teststudio/test-studio-runtime" target="_blank">Test Studio Run-Time edition</a> installed on the remote machine and the Profiler Service enabled. The versions of Test Studio run locally and remotely on the server must match. Also ensure the correct inbound and outbound ports are open on the remote server.

## How to Open a Port on the Machine?

The below steps will guide you how to open a port on any machine.

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
