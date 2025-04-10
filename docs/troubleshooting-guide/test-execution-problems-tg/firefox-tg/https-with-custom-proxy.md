---
title: HTTPS with Custom Proxy
page_title: Firefox HTTPS Error with Custom Proxy
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Firefox HTTPS Error with Custom Proxy

## PROBLEM

I receive the following error when executing a test against an HTTPS site using Firefox configured with a custom proxy:

*This Connection is Untrusted.<br>
You have asked Firefox to connect securely to www.domain.com, but we can't confirm that your connection is secure.*


![Untrusted][1]

## SOLUTION

1.&nbsp; Register the certificate for HTTPS Connection.

a. Follow the instructions <a href="/knowledge-base/project-configuration-kb/register-certificate" target="_blank">here</a>.

2.&nbsp; Export the Fiddler Root Certificate.

 a. Open <a href="http://www.telerik.com/download/fiddler" target="_blank">Fiddler</a>.

 b. Click **Tools > Fiddler Options**.
 
 c. Select the **HTTPS** tab.

 d. Click the **Export Root Certificate to Desktop** button.

![Export][2]

3.&nbsp; Configure Firefox to trust the Fiddler Root Certificate.

 a. Open Firefox.

 b. Click **Tools > Options**.

 c. Click **Advanced**.

 d. Click the **Encryption** tab.

 e. Click **View Certificates**.

 f. Click the **Authorities** tab.

 g. Click **Import**.

 h. Select *FiddlerRoot.cer* from the Desktop.

 i. Check **Trust this CA to identify websites**.

![Download Cert][3]

 j. Click **OK**.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/firefox-tg/https-with-custom-proxy/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/firefox-tg/https-with-custom-proxy/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/firefox-tg/https-with-custom-proxy/fig3.png