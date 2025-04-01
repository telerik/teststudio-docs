---
title: Test Results (VS Plugin)
page_title: Test Results (VS plugin)
description: "Review Test Studio Test Results in Visual Studio. Where to find the  the Test Studio test execution results from Test Explorer run. Where to find the  the Test Studio test execution results from quick execution run."
position: 6
---
# Test Results from Tests Executed in Visual Studio

The Test Studio tests created in a Visual Studio project can be executed both from the Test Studio engine via the Quick run option, or from the Test Explorer of the Visual Studio. The generated results provide different set of benefits for maintaining the test.

In this article you can find more about the results from test runs in Visual Studio: 

* [Test execution via the Test Studio engine](#quick-execution-of-test-studio-test)
* [Test execution via the Visual Studio Test Explorer](#executing-test-studio-test-via-test-explorer)

## Quick Execution of Test Studio Tests

All <a href="/automated-tests/test-execution/quick-execution" target="_blank">__Quick Execution__ options</a> from Test Studio project are also available in the context of the Visual Studio project. The __Execute__ button is in the test toolbar when a test is opened in the project and is enabled when the test has at least one step to execute.

![Execute test](/img/general-information/create-test-vsplugin/web-test/execute-test.png)

After the __Quick Execution__ of a test, you can explore the <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">generated quick execution log and, in case of failure - failure details</a>, in the same fashion as the Test Studio IDE allows.

## Executing Test Studio Test via Test Explorer

When executing the tests from the <a href="/getting-started/test-execution/vs-2012-test-explorer" target="_blank">Visual Studio Test Explorer</a> you can see the results in the  pane of the Test Explorer - depending on the layout you are using this can be under or next to the list of tests.

![View test results 2012][6]




[6]: /img/general-information/test-results/test-results-vs/fig6.png
