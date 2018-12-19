---
title: Visual Studio Test Explorer
page_title: Visual Studio Test Explorer
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-execution/visual-studio-2012-test-explorer.aspx, /user-guide/test-execution/visual-studio-2012-test-explorer
position: 1
---
# Visual Studio Test Explorer #

As of Update 1, Visual Studio 2012 deprecates <a href="http://msdn.microsoft.com/en-us/library/dd293547.aspx" target="_blank">Test View</a> and <a href="http://msdn.microsoft.com/en-us/library/dd286595.aspx" target="_blank">Test Lists</a>. The <a href="http://msdn.microsoft.com/en-us/library/hh270865.aspx" target="_blank">Test Explorer</a> discovers and runs tests, including Test Studio tests.

To open Test Explorer go to **Test > Windows > Test Explorer**:

![Test tab][1]

The Test Explorer lists the Test Studio tests within the currently opened solution.

![Test Explorer][2]

Test Explorer can list tests using five criteria: class, duration, outcome, traits, and project. Test Studio tests currently support sorting by **Class**, **Duration**, and **Outcome**.

![Sort][3]

To execute specific tests in the Test Explorer, use **Run...** and select a criterion.

![Run][4]

> Note: When executing tests from Test Explorer <a href="/features/project-settings/overview" target="_blank">Test Studio test settings</a> are not applied. To use the default Test Studio settings it will be necessary to add a project settings file and apply it for Test Explorer test execution as shown <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">here</a>.

[1]: /img/getting-started/test-execution/vs-2012-test-explorer/fig1.png
[2]: /img/getting-started/test-execution/vs-2012-test-explorer/fig2.png
[3]: /img/getting-started/test-execution/vs-2012-test-explorer/fig3.png
[4]: /img/getting-started/test-execution/vs-2012-test-explorer/fig4.png
