---
title: Tests In Development
page_title: Tests In Development
description: "Test Studio Tests In Development each test or standalone code file could be set into 'In Development' state. If the test includes a code file it will be automatically set to 'In Development' along with the test"

position: 1
---
# Tests In Development

Test Studio allows setting each test or standalone code file into 'In Development' state. If the test includes a code file it will be automatically set to 'In Development' along with the test.

![Set In Development State](/img/features/test-maintenance/tests-in-development/right-click-test.png)

Each test marked as 'In Development' will be **displayed in red** in the <a href="/features/project-explorer/overview" target="_blank">Project Explorer</a>. If the test includes a code file its name will be also coloured in red.

![Code Files in development](/img/features/test-maintenance/tests-in-development/test-in-dev-mark.png)

**Load and Manual** tests could not be set 'In Developement' as these do not require compilation.

## Tests In Development As Test As Step

If a test flagged as 'In Development' is included as a **test as step** in any other test it will be always attemped to be executed regardless of its current state. 

## Tests In Development In Test Lists

Any tests could be included in a test list. These marked as **'In Development'** will be coloured in red also in the 'Create New Test List' wizard. 

![Create Test List](/img/features/test-maintenance/tests-in-development/test-in-dev-test-list.png)

Depending on the <a href="/getting-started/test-execution/test-list-settings" target="_blank">test list setting</a> **'ExecuteTestsInDevelopment'** the tests marked as 'In Development' will be either skipped or executed for both local and remote run. The default behavior is these to be skipped.

![Test List Execution](/img/features/test-maintenance/tests-in-development/test-in-dev-list-settings.png)

To remove the 'In Development' flag select the 'Remove' option from a test's context menu in the Project Explorer. 

![Remove In Development State](/img/features/test-maintenance/tests-in-development/right-click-remove-dev.png)

