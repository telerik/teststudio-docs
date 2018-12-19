---
title: Add Existing Test Script
page_title: Add Existing Test Script
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Add Existing Test Script #

If you would need to reuse a test from another project the easiest and safest way would be to use the built-in option to import existing test files as shown on the screenshot bellow:

![Add existing file][1]

With this approach you ensure the test would keep its **UniqueID** property really unique in the new project as well. If the files are maintained outside of Test Studio (Windows Explorer) might lead to duplicating that property which could lead to misbehaivor if the tests are being executed <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">scheduled</a> or <a href="/features/scheduling-test-runs/run-list-remotely" target="_blank">remotely</a>. Duplicated UniqueID property in a project could lead to duplicated entries in the Storage serveice database and result in misbehavior when executing test lists.

[1]: /img/knowledge-base/best-practices-kb/add-existing-test/fig1.png
