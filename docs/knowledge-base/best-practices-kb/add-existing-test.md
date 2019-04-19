---
title: Add Existing Test Script
page_title: Add Existing Test Script
description: How to add an existing test in a new project. A test designed in one project can be reused in another. 
position: 1
---
# Add Existing Test Script #

If you would need to reuse a test from another project the easiest and safest way would be to use the built-in option to import existing test files as shown on the screenshot below:

![Add existing file][1]

With this approach you ensure the test would keep its **UniqueID** property really unique in the new project as well. If the files are maintained outside of Test Studio (Windows Explorer) might lead to duplicating that property which could lead to misbehaivor if the tests are being executed <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">scheduled</a> or <a href="/features/scheduling-test-runs/run-list-remotely" target="_blank">remotely</a>. Duplicated UniqueID property in a project could lead to duplicated entries in the Storage serveice database and result in misbehavior when executing test lists.

[1]: /img/knowledge-base/best-practices-kb/add-existing-test/fig1.png
