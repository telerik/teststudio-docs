---
title: No Internet Connection
page_title: No Internet Connection
description: "Progress® Test Studio® for APIs - Troubleshooting guide - No Internet Connection"
previous_url: /troubleshooting-guide/deregister-proxy
position: 3
publish: true
---

#No Internet Connection

If the process of Test Studio for APIs (Telerik.ApiTesting.exe) is forced to stop unexpectedly (e.g. in case of a computer power off or killing the process from the Windows Task Manager) while [HTTP Recording](/features/record/http-traffic) is running, you may experience problems connecting to the Internet.

![No Internet Connection][3]

This happens because when <a href="/features/record/http-traffic">recording http traffic</a> is started ApiTesting will register as a proxy in:

`Windows Start Menu > Internet Options > Connections tab > LAN Settings > Proxy Server`

![Proxy][1]

In Windows 10 you can also get to the proxy settings by hitting the Windows Start button and typing Network proxy settings, you get the window provided below:

![Proxy][2]

Normally, when recording is stopped, ApiTesting will deregister as a proxy (the checkbox in the the screenshot above should be unchecked). 

When the Telerik.ApiTesting.exe process is killed unexpectedly, the proxy may remain registered (checkbox checked) even if you are not capturing traffic.
This may result in breaking the Internet connection on the machine you are working on. If you experience similar issues, please refer to the Proxy Server settings and **uncheck the checkbox manually**.

[1]: /img/troubleshooting-guide/deregister-proxy/registered-proxy.png
[2]: /img/troubleshooting-guide/deregister-proxy/windows10.png
[3]: /img/troubleshooting-guide/deregister-proxy/no-internet-connection.png

