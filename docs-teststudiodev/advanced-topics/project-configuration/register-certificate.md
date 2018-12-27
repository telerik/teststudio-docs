---
title: Register Certificate
page_title: Register Certificate | Test Studio Dev Documentation
description: Register https certificate 
position: o
---
# Register Certificate for HTTPS Connection

If the web application you are trying to automate is accessible via secure HTTP (HTTPS) with a URL like this:

* https://www.something.com

you might encounter certificate-related warnings when the __Test Studio Dev__ recorder or runner is attached to the browser although the error does not appear if accessing the application directly in a browser.

![Certificate][1]

[1]: images/register-certificate/fig1.png
[2]: images/register-certificate/fig2.png
[3]: images/register-certificate/fig3.png

This is expected behavior and it's related to the way Test Studio Dev hooks into the browser. If this warning is a problem for your test automation, use the **Register certificate** for https connection feature:

1.Load <a href="/features/project-settings/overview" target="_blank">Project Settings</a> and go to the Others section.

2.Click **Register certificate for https connection** under *Connection settings*.

![Register certificate][2]

3.You are prompted to install a certificate. Click Yes. After installing the certificate, you will no longer receive the certificate-related warning when automating your application with Test Studio.

![Security Warning][3]

> Ensure that installing the certificate does not violate your company's security policies.

**Note**:  If clicking "Register certificate for https connection" button does not bring the security warning above, this might be due to specific Security Policy that overrides the local administrator rights. In such cases there is a workaround by installing <a href="http://www.telerik.com/fiddler" target="_blank">Fiddler</a> and using it to install the required certificate into the Machine Trusted Root Certificates folder.

## Install the Certificate from Command Line 

Open a command prompt and navigate to the following directory:

* **C:\Program Files (x86)\Progress\Test Studio\Bin**

Then enter the following command:

```
ArtOfTest.WebAii.HttpProxy.exe InstallCertificate
```