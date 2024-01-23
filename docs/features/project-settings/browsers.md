---
title: Browsers Configuration Settings
page_title: Browsers Configuration Settings
description: "Test Studio project settings related to Browsers support. How to configure browser specific settings in Test Studio. Configure browsers in Test Studio. Calibrate Browsers in Test Studio. Set Preferred browser for recording and execution"
position: 4
---
# Browsers

Under the __Browsers__ tab in _Project Settings_, you can set your preferred browser, check if an update for latest browser versions is available, and calibrate the supported browsers.

![Browsers][1]

> Check <a href="/features/project-settings/overview" target="_blank">here how to open the **Project Settings** window</a>. 

## Preferred Browser

Select an installed and supported browser from the __Preferred Browser__ section to set it as the default test recording and quick execution browser for web tests and <a href="/automated-tests/responsive/responsive-test" target="_blank">responsive web tests</a> (responsive web tests support only Chrome and Edge Chromium).

![Preferred Browser][2]

> *Preferred browser* for web test can be set from the <a href="/automated-tests/test-execution/quick-run-browsers" target="_blank">Test ribbon</a>.

## Browser Support Updater

Striving to be up-to-date with the latest browser versions, Test Studio regularly <a href="/features/dialogs-and-popups/dialog-handler-updater" target="_blank">updates the support</a> of any recent changes in browsers' new releases. A notification that there is an update appears, when one is available.

![Dialog Handler Update][3]

## Extension

Enable/Disable using extension for <a href="/prerequisites/configure-your-browser/chrome" target="_blank">Chrome browser automation</a>.

## Calibration

The _Calibrate Browser_ section allows the <a href="/prerequisites/configure-your-browser/browser-configuration" target="_blank">configuration of supported browsers for use with Test Studio</a>. Click **Calibrate** next to a browser to update its settings to be compatible for test recording and execution.

![Calibrate][5a]

A warning message appears that any running instances of the selected browser will be closed during the calibration. Confirm, if you want to proceed, or cancel, if you need to save any data in the running browser.

![Confirm][4]

To restore the original browser settings that were in place before calibration, click **Restore**.

![Restore][5]

> __Note!__ If your Chrome browser has an active Google Apps session (for example, you are logged into GMail), automatic calibration will not work as expected. To use automatic configuration, log out of your Google account first.

[1]: /img/features/project-settings/browsers/fig1.png
[2]: /img/features/project-settings/browsers/fig2.png
[3]: /img/features/project-settings/browsers/fig3.png
[4]: /img/features/project-settings/browsers/fig4.png
[5]: /img/features/project-settings/browsers/fig5.png
[5a]: /img/features/project-settings/browsers/fig5a.png
