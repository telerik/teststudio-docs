---
title: Build Server Test Execution
page_title: Build Server Test Execution
description: "Build Server Test Studio Test Execution."
previous_url: /user-guide/command-line-test-execution.aspx, /user-guide/command-line-test-execution
position: 2
---
#Build Server Test Execution#

> A minimum of Test Studio <a href="/general-information/test-studio-run-time" target="_blank">Run-Time Edition</a> is required on your build server.

Here are your options for command line test execution of tests and test lists:

* <a href="/features/test-runners/mstest" target="_blank">MSTest.exe</a> - use Microsoft's command line utility to execute <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests.

* <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner.exe</a> - use Test Studio's built-in execution engine.

* <a href="/advanced-topics/build-server/continious-integration-overview" target="_blank">Continuous Integration</a> - run automated tests against newly compiled and verified builds.

* <a href="/features/test-runners/manual-runner" target="_blank">Telerik.TestStudio.ManualRunner</a> - launch the Manual test runner.

![Conceptual diagram][1]

*TFS Build Server / MTM Configuration conceptual diagram.*

[1]: /img/advanced-topics/build-server/build-servers-test-execution/fig1.png