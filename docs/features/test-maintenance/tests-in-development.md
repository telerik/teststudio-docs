---
title: Tests In Development
page_title: Tests In Development
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."

position: 1
---
# Tests In Development

As of version 2017 R3 each test or standalone code file could be set into 'In Development' state. If the test includes a code file it will be automatically set to 'In Development' along with the test.

![Set In Development State][1]

Each test marked as 'In Development' will be **displayed in red** in the <a href="/features/project-explorer/overview" target="_blank">Project Explorer</a>. If the test includes a code file its name will be also coloured in red.

![Code Files in development][2]

**Load and Manual** tests could not be set 'In Developement' as these do not require compilation.

## Tests In Development As Test As Step

If a test flagged as 'In Development' is included as a **test as step** in any other test it will be always attemped to be executed regardless of its current state. 

## Tests In Development In Test Lists

Any tests could be included in a test list. These marked as **'In Development'** will be coloured in red also in the 'Create New Test List' wizard. 

![Create Test List][3]

Depending on the <a href="/getting-started/test-execution/test-list-settings" target="_blank">test list setting</a> **'ExecuteTestsInDevelopment'** the tests marked as 'In Development' will be either skipped or executed for both local and remote run. The default behavior is these to be skipped.

![Test List Execution][4]

To remove the 'In Development' flag select the 'Remove' option from a test's context menu in the Project Explorer. 

![Remove In Development State][5]

[1]: /img/features/test-maintenance/tests-in-development/fig1.png
[2]: /img/features/test-maintenance/tests-in-development/fig2.png
[3]: /img/features/test-maintenance/tests-in-development/fig3.png
[4]: /img/features/test-maintenance/tests-in-development/fig4.png
[5]: /img/features/test-maintenance/tests-in-development/fig5.png