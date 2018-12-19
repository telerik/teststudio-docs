---
title: Cannot Build Project After version 2015.3.1202 
page_title: Cannot Build Project After version 2015.3.1202 
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Cannot build projects in Visual Studio after upgrading to 2015.3.1202 version and higher

## PROBLEM

 The problem occurs after upgrading the <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> Visual Studio plugin to 2015.3.1202 version. In Visual Studio your test projects will no longer build. 

![Erros][1]

# SOLUTION

As of version **2015.3.1202** Test Studio has migrated to **.NET 4.5**. If your test project was created in .NET 4.0 the above issue will occur after upgrading the Test Studio Visual Studio plugin to version 2015.3.1202 and above.

You have to upgrade your Visual Studio projects to **.NET Framework 4.5** as the target framework from the properties of the Test Project.

1.&nbsp; Right click on the test project and click **Properties**.

![Properties][2]

2.&nbsp; Under the Application tab select **.NET Framework 4.5** as the target framework.

![Target framework][3]

3.&nbsp; Confirm the target framework change. 

![Confirm the changes][4]

[1]: /img/troubleshooting-guide/visual-studio-tg/cannot-build-project/fig1.png
[2]: /img/troubleshooting-guide/visual-studio-tg/cannot-build-project/fig2.png
[3]: /img/troubleshooting-guide/visual-studio-tg/cannot-build-project/fig3.png
[4]: /img/troubleshooting-guide/visual-studio-tg/cannot-build-project/fig4.png
