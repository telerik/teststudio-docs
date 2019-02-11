---
title: Extension Not Installed
page_title: Safari Extension Not Installed
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Safari Extension Not Installed

## PROBLEM

I cannot execute a test in Safari. I receive the following message:

*Safari automation extension has not yet been installed. Please click 'Install' when
prompted to install the WebUI automation extension and close the Safari window
once the extension has been installed.*

![Not installed][1]

## SOLUTION

If things go as expected, clicking OK on the above message should load Safari and display the prompt below. Click **Install** to proceed. Once finished, your test should execute in Safari. 

![Install][2]

If the test does not execute, or you never receive the second prompt, install the Safari extension manually:

1.&nbsp; Locate the following file:

 - **C:\Program Files (x86)\Telerik\Test Studio\Browser Extensions\Safari\WebUI.safariextz**

2.&nbsp; Right click the file and select **Open with**.

![Open With][3]

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

3.&nbsp; Open the file with Safari to install the extension. 

![Safari][4]

4.&nbsp; Retest Safari execution in Test Studio.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/safari-tg/extension-not-installed/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/safari-tg/extension-not-installed/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/safari-tg/extension-not-installed/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/safari-tg/extension-not-installed/fig4.png