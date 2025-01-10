---
title: Configure Custom Proxy
page_title: Configure Custom Proxy
description: "Progress® Test Studio® for APIs - CI Server Integration"
position: 2
published: true
---

# Overview

TestStudio for APIs uses the default system proxy settings (a.k.a. WinInet Windows settings)  which are the same settings that Internet Explorer
uses and that are configured in the Windows and Internet Explorer Internet Settings dialog. 
This is a nice <a href="https://www.securelink.be/windows-proxy-settings-explained/">article</a> that gives more information on the topic.

## Configure Custom Proxy

You can configure custom proxy by opening:

`Windows Start Menu > Internet Options > Connections tab > LAN Settings > Proxy Server`

![Proxy][1]

Check "Use a proxy server for your LAN ..." and click the Advanced button to add the IP/URL and port for your proxy server 
(you will need to add those for both HTTP and Secure types in order to route https requests. 

Another way to access the Internet Options is if you open Internet Explorer and click on Internet Options.

These settings will be applied not only to Test Studio for APIs, but for Internet Explorer and other applications (not all windows applications use them though).

[1]: /img/troubleshooting-guide/deregister-proxy/registered-proxy.png