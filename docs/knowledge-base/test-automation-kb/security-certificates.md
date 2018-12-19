---
title: Security Certificates
page_title: Security Certificates
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Security Certificates#

Security (SSL) Certificates are tricky to automate because each browser prompts its warning differently. Because Test Studio only records in Internet Explorer, the "Continue to this website" link pictured below is recorded and expected to pass when executed in IE. That specific link does not exist in the other browsers, so we expect the test to fail at that step in Firefox, Safari, and Chrome.

**Internet Explorer**

![Security warning][1]

**Chrome**

![Security warning Chrome][2]

**FireFox**

![Security warning FireFox][3]

**Safari**

![Security warning Safari][4]

##Solution##

There are a few work-arounds to consider:

1. Register <a href="/knowledge-base/project-configuration-kb/register-certificate" target="_blank">Certificate for HTTPS Connection</a>.

2. Change the browser settings to not prompt for certificates. In Firefox this setting is located under:
	* **Tools > Options > Advanced > Encryption > Certificates > Select one automatically**

3. Add a <a href="/features/custom-steps/manual-step" target="_blank">Manual Step</a>. This will require the tester to manually accept the certificate during test execution and then press OK on the Manual Step dialog to continue. You can set the Manual Step's "RunsAgainst" property to "FirefoxOnly" and set the step that clicks the link in the image above to "InternetExplorerOnly". This way, executing in IE remains automated and only executing in an alternative browser requires manual intervention.

4. Add a <a href="/features/custom-steps/script-step" target="_blank">Coded Step</a>. The code will perform different actions (such as mouse clicks and/or key presses) based on which browser is used. This will handle the different Certificate screens you encounter across browsers. Here's an example for Chrome:

```C#
if (ActiveBrowser.BrowserType == BrowserType.Chrome)
{
    Manager.Desktop.KeyBoard.KeyPress(System.Windows.Forms.Keys.Tab);
    Manager.Desktop.KeyBoard.KeyPress(System.Windows.Forms.Keys.Space);
}
```
 

```VB
If ActiveBrowser.BrowserType = BrowserType.Chrome Then
    Manager.Desktop.KeyBoard.KeyPress(System.Windows.Forms.Keys.Tab)
    Manager.Desktop.KeyBoard.KeyPress(System.Windows.Forms.Keys.Space)
End If
```

[1]: /img/knowledge-base/test-automation-kb/security-certificates/fig1.png
[2]: /img/knowledge-base/test-automation-kb/security-certificates/fig2.png
[3]: /img/knowledge-base/test-automation-kb/security-certificates/fig3.png
[4]: /img/knowledge-base/test-automation-kb/security-certificates/fig4.png


