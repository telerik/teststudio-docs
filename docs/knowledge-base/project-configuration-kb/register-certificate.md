---
title: Register Certificate
page_title: Register Certificate
description: Register Certificate for HTTPS Connection. I encounter certificate-related warnings when the Test Studio recorder or runner is attached to the browser
previous_url: /user-guide/knowledge-base/project-configuration/register-certificate-for-https-connection.aspx, /user-guide/knowledge-base/project-configuration/register-certificate-for-https-connection
position: 1
---
#Register Certificate for HTTPS Connection#

I'm working on a web application accessible via secure HTTP (HTTPS) with a URL like this:

* https://www.something.com

I encounter certificate-related warnings when the Test Studio recorder or runner is attached to the browser. I do not see this warning when the recorder or runner is not attached:

![Certificate][1]

[1]: /img/knowledge-base/project-configuration-kb/register-certificate/fig1.png
[2]: /img/knowledge-base/project-configuration-kb/register-certificate/fig2.png
[3]: /img/knowledge-base/project-configuration-kb/register-certificate/fig3.png

##Standalone version and VS plugin##

This is expected behavior and it's related to the way Test Studio hooks into the browser. If this warning is a problem for your test automation, use the **Register certificate** for https connection feature:

1. Load <a href="/features/project-settings/General" target="_blank">Project Settings</a> and go to the Others section.

2. Click **Register certificate for https connection** under *Connection settings*.

	![Register certificate][2]

3. You are prompted to install a certificate. Click Yes. After installing the certificate, you will no longer receive the certificate-related warning when automating your application with Test Studio.

	![Security Warning][3]

> Ensure that installing the certificate does not violate your company's security policies.

**Note**:  If clicking "Register certificate for https connection" button does not bring the security warning above, this might be due to specific Security Policy that overrides the local administrator rights. In such cases there is a workaround by installing <a href="http://www.telerik.com/fiddler" target="_blank">Fiddler</a> and using it to install the required certificate into the Machine Trusted Root Certificates folder.

##Run-Time Edition##

Without a full version of Test Studio installed, there is no GUI to register the certificate as outlined above. This can be done from the command line, however.

Open a command prompt and navigate to the following directory:

* **C:\Program Files (x86)\Telerik\Test Studio\Bin**

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

Then enter the following command:

```
ArtOfTest.WebAii.HttpProxy.exe InstallCertificate
```

##See Also##

* <a href="/knowledge-base/test-automation-kb/security-certificates" target="_blank">Security Certificates</a>