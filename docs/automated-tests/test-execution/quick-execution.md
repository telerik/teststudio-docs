---
title: How to Execute Test
page_title: Execute Your First Test in Test Studio
description: "Test Studio Quick test Execution. Run a Test Studio test. Choose browser to execute the test against."
position: 0
---
# How to Execute Test

Once you have recorded a test in Test Studio, you can proceed with its execution. The Quick Execution mode provides different mechanisms for adjusting the test runs and helps you identify if additional test adjustment is required.

## Execute a Test

Once you have recorded your first test scenario, you can review the steps into it and execute these against any of the supported browsers. To trigger the test run, lick the **Execute** button in the Test ribbon.

![Test Studio][1]

The next dialog allows you to select the browser to run the test against. Select any of the listed for execution browsers and click the __Run__ button.

![Select browser][2]

> __Tip__
> <br>
> <br>
> This step will be skipped if you have already set a preferred browser from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Web ribbon</a>.

The selected browser is launched from Test Studio on top of any other running apps and the recorded steps are being executed accordingly.

> __Important__
> <br>
> <br>
> While a test is being executed **do not start another instance of the same browser or any other application** until the run is finished!

## Quick Run Results

The quick run execution mode results are dedicated mainly for debugging any inconsistencies in the recorded test steps. Therefore, these are only temporary results for the last initiated run. These will be overridden when the test is executed again using the __Execute__ button, or deleted - if the test/project is closed and reopened.

> __Tip__
> <br>
> <br>
> Once the test is adjusted and demonstrates consistent execution behavior, you can include it in a test list and trigger the test run through it, where the generated results are being stored. !!!! link to be added !!!! modify !!!  <a href="/getting-started/test-execution/quick-execution" target="_blank">link to the test list page</a>.

Once the test run is finished, you can check its overall status - whether this is passed or failed, check the complete execution log and the failure details for the failing step, if applicable.

![Quick run results][3]

## Options to Modify for the Quick Test Run

Test Studio provides multiple options to ease you in executing the tests and debug any encountered failures. You can access some of these directly through the **Test** ribbon. Below you can find a list of these quick access tools with a link redirecting to further details for the available options.

- Set Preferred Browser
- Calibrate the Browsers
- Set a BaseURL and Compare mode
- Change the Execution Timeouts on project level
- Enable the Test Studio Visual Debugger tool
- Enable Annotations during test run


[1]: /img/automated-tests/test-execution/quick-execution/fig1.png
[2]: /img/automated-tests/test-execution/quick-execution/fig2.png
[3]: /img/automated-tests/test-execution/quick-execution/fig3.png