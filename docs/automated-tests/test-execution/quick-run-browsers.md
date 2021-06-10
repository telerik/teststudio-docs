---
title: Browser Control in Quick Execution
page_title: Browser Control in Quick Execution
description: "Learn how to set a preferred browser for Test Studio's quick test execution and how to calibrate a browser."
position: 2
---
# Browser Control in Quick Execution

The **Test** ribbon in Test Studio allows you to trigger a quick test execution and provides access to project settings like preferred browser and browser calibration.

## Preferred Browser

Test Studio allows you to set a preferred browser for the current project so that you can use this browser in each test run. This is helpful in the following scenarios:

* The application under test is used mainly in one browser.

* There is a requirement to test the application in a specific browser.

The **Preferred browser** setting applies to all tests in the current project. You can modify it in the project's **Settings**. Additionally, you can choose the preferred browser in the **Test** ribbon's **Preferred browser** dropdown. The dropdown list allows you to select from the following options:

* One of the installed browsers.

* The OS default browser.

* The **Ask me every time** option.

![Preferred browser dropdown][1]

## Calibrate Browsers

The browser calibration is a collection of settings that makes the browser compatible for recording and executing automated tests with Test Studio. Test Studio can automatically apply these settings to the installed browsers.

To access the built-in browser calibration, go to the **Test** ribbon and click **Calibrate browsers**. This will open the project **Settings** dialog with the **Calibrate** buttons.

![Calibrate browser quick access][2]

[1]: /img/automated-tests/test-execution/quick-run-browsers/fig1.png
[2]: /img/automated-tests/test-execution/quick-run-browsers/fig2.png
