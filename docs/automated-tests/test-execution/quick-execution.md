---
title: How to Execute Test
page_title: Execute Your First Test in Test Studio
description: "Test Studio Quick test Execution. Run a Test Studio test. Choose browser to execute the test against."
position: 0
---
# How to Execute Test

__Quick Test Execution__ in Test Studio is a key feature, which helps in fine tuning the recorded actions, adjust test and step settings, to eventually introduce stable and consistent behavior of the test runs in test list mode, executed on different environments.

This article will guide you through the execution process in details.

## Execute a Test

Once you have <a href="/automated-tests/recording/overview" target="_blank">recorded a complete test scenario</a>, the steps, which represents the recorded actions, are listed in the _Test Steps_ pane. These steps can be __executed against any of the supported browsers__, regardless of the browser they were recorded against. To trigger the test run, click the **Execute** button in the ___Test___ ribbon.

![Test Studio][1]

In the next dialog, which appears on the screen, __choose the browser to run the test against__. Select any of the browsers listed for execution and click the __Run__ button.

![Select browser][2]

> __Tip__
> <br>
> <br>
> This dialog will not appear, if you have already <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set a preferred browser from the __Test__ ribbon</a>.

The selected browser is launched from Test Studio on top of any other running apps, and the recorded steps are being executed accordingly.

![Test Studio][4]

> __Important__
> <br>
> <br>
> While a test is being executed **do not start another instance of the same browser or any other application** until the run is finished!

## Quick Run Results

The <a href="/automated-tests/test-results/analyze-quick-run-results" target="_blank">results from the quick execution</a> mode are dedicated mainly for <a href="/automated-tests/troubleshooting/failing-test" target="_blank">debugging any inconsistencies</a> in the recorded test steps. Therefore, these are only __temporary results for the last initiated run__. These will be overridden when the test is executed again using the __Execute__ button, or deleted - if the test/project is closed and reopened.

Once the test run is finished, the Test Steps pane displays the overall result - whether the test is passed or failed, which step failed, if any. You can also access a complete execution log and the <a href="/automated-tests/test-results/step-failure-details" target="_blank">failure details</a> for the failing step, if applicable.

![Quick run results][3]

> __Tip__
> <br>
> <br>
> Once the test is adjusted and demonstrates consistent execution behavior, you can <a href="/automated-tests/test-lists/test-lists-standalone" target="_blank">include it in a test list</a>. The results generated from test list runs are being stored on project level.

## Options to Modify for the Quick Test Run

Test Studio provides multiple options to ease you in executing the tests and debugging any encountered failures. The mostly used settings are added in the ___Quick Test Execution___ ribbon for quick access. Details for these quick access options can be found in the referenced articles below:

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