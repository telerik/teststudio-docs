---
title: Register Certificate
page_title: Register Certificate - Test Studio Dev Documentation
description: "Register https certificate, I encounter certificate-related warnings when the Test Studio recorder or runner is attached to the browser. Load Test cannot navigate to the desired page due to security warning certificate error"
position: 0
---
# Register Certificate for HTTPS Connection

If the web application you are automating is accessible via secure HTTP (HTTPS), you might encounter warnings for the website's security certificate against https pages.

## Problem

I'm working on a web application accessible via secure HTTP (HTTPS) with a URL like this `https://www.something.com`. I encounter certificate related warnings when the Test Studio recorder or runner is attached to the browser. I do not see this warning when the recorder or runner is not attached.

![Certificate][1]

[1]: images/register-certificate/fig1.png
[2]: images/register-certificate/fig2.png
[3]: images/register-certificate/fig3.png

## Solution

This is expected behavior and it's related to the way Test Studio Dev hooks into the browser. If this warning is a problem for your test automation, use the **Register certificate** for https connection feature:

1.Open the <a href="/features/project-settings/overview" target="_blank">Project Settings</a> and go to the General section.

2.Click **Register certificate for https connection** under *Connection settings*.

![Register certificate][2]

3.You are prompted to install a certificate. Click Yes. After installing the certificate, you will no longer receive the certificate-related warning when automating your application with Test Studio.

![Security Warning][3]

> Ensure that installing the certificate does not violate your company's security policies. </br>

> **Note!**  If clicking "Register certificate for https connection" button does not bring the security warning above, this might be due to specific Security Policy that overrides the local administrator rights. In such cases there is a workaround by installing <a href="http://www.telerik.com/fiddler" target="_blank">Fiddler</a> and using it to install the required certificate into the Machine Trusted Root Certificates folder.

## Install the Certificate from Command Line

Open a command prompt and navigate to the __Test Studio Dev__ installation directory `C:\Program Files (x86)\Progress\Test Studio\Bin`. Then enter the following command to install the security certificate:

```
ArtOfTest.WebAii.HttpProxy.exe InstallCertificate
```
