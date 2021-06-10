---
title: How to Execute Tests
page_title: Execute Your First Test in Test Studio
description: "Learn how to execute quick tests in Test Studio, modify the quick tests, and access the test results"
position: 0
---
# How to Execute Tests

__Quick Test Execution__ helps you fine tune the recorded actions, test, and step settings. It helps you achieve stable and consistent test behavior in test list mode when you execute the test in different environments.

This article guides you through the quick test execution process in details.

## Execute a Test

Once you have <a href="/automated-tests/recording/overview" target="_blank">recorded a complete test scenario</a>, the steps, which represents the recorded actions, are listed in the __Test steps__ pane. You can execute these steps against any of the supported browsers, regardless of the browser that you used to record them. 

To trigger the test run, click the **Execute** button in the __Test__ ribbon.

![Test Studio][1]

In the __Executing__ dialog, choose the browser for the test, and then click __Run__.

![Select browser][2]

> __Tip__
> <br>
> <br>
> This dialog will not appear if you have already <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set a preferred browser from the __Test__ ribbon</a>.

Test Studio launches the selected browser on top of any other running apps and executes the recorded steps.

![Test Studio][4]

> __Important__
> <br>
> <br>
> Do not start another instance of the same browser or any other application until the test completes!

## Quick Run Results

The <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">results from the quick execution</a> mode are dedicated mainly to <a href="/automated-tests/troubleshooting/failing-test" target="_blank">debugging inconsistencies</a> in the recorded test steps. Therefore, these are only temporary results for the last test run. These results will be overwritten when you execute the test again or deleted if you close and reopen the test/project.

Once the test completes, the __Test steps__ pane displays the overall result - passed or failed and any failed steps. You can also access a complete execution log and the <a href="/automated-tests/test-results/step-failure-details" target="_blank">failure details</a> for the failing step.

![Quick run results][3]

> __Tip__
> <br>
> <br>
> Once you adjust the test and it demonstrates consistent execution behavior, you can <a href="/automated-tests/test-lists/test-lists-standalone" target="_blank">include it in a test list</a>. The results generated from test list runs are stored on project level.

## Options to Modify for the Quick Test Run

Test Studio provides multiple options that ease you in executing the tests and debugging any encountered failures. The most used settings are added in the __Tests__ ribbon for quick access. For more details on the quick access options, see the articles below:

- <a href="/automated-tests/test-execution/quick-run-browsers" target="_blank">Set Preferred Browser</a>
- <a href="/automated-tests/test-execution/quick-run-browsers#calibrate-browsers" target="_blank">Calibrate the Browsers</a>
- <a href="/automated-tests/test-execution/quick-run-baseurl" target="_blank">Set a BaseURL and Compare mode</a>
- <a href="/automated-tests/test-execution/quick-run-timeouts" target="_blank">Change the Execution Timeouts on project level</a>
- <a href="/automated-tests/test-execution/quick-run-visual-debugger" target="_blank">Enable the Test Studio Visual Debugger tool</a>
- <a href="/automated-tests/test-execution/quick-run-annotations" target="_blank">Enable Annotations during test run</a>

[1]: /img/automated-tests/test-execution/quick-execution/fig1.png
[2]: /img/automated-tests/test-execution/quick-execution/fig2.png
[3]: /img/automated-tests/test-execution/quick-execution/fig3.png
[4]: /img/automated-tests/test-execution/quick-execution/execute-test.gif