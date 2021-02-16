---
title: Browser Control in Quick Execution
page_title: Browser Control in Quick Execution
description: "Test Studio Quick test Execution. How to Set preferred browser for test runs and test recording. Wuick Access the browser calibration tool"
position: 1
---
# Browser Control in Quick Execution

The **Test Ribbon** in Test Studio allows you to trigger a quick test execution. Along with that it provides quick access to some useful project settings.

## Preferred Browser

If the application under test is mainly used in one browser, or there is a requirement to test in specific browser, it would be waste of time to choose the executing browser for each test run. Therefore Test Studio allows you to set one of the supported browser as a preferred one for the current project - that way this browser will be triggered for each recording session and quick run of the test. This setting is global for the current project and can be modified in the Project Settings.

The **Test Ribbon** provides you quick access to choose a default browser. Under the **Preferred browser** section you can access a dropdown to set your preferred browser for this project. The list contains all installed browsers or the option to select the OS default set browser. Leaving the dropdown option _'Ask me every time' will allow you to choose the browser by each recording session or quick execution.

![Preferred browser dropdown][1]

## Calibrate Browsers

The browser calibration is a required set of settings, which makes the browser compatible for recording and executing automated tests with Test Studio. Test Studio provides the option to automatically apply the necessary settings for the installed browsers in the Project Settings. 

The **Test Ribbon** in Test Studio provides you quick access to this built-in tool for automatic browser calibration.

![Calibrate browser quick access][2]

[1]: /img/automated-tests/test-execution/quick-run-browsers/fig1.png
[2]: /img/automated-tests/test-execution/quick-run-browsers/fig2.png
