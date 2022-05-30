---
title: Browsers Configuration Settings
page_title: Browsers Configuration Settings | Test Studio Dev Documentation
description: "Configure browsers to be used for recording and execution with Test Studio Dev."
position: 4
---
# Browsers Tab in Project Settings

Under the Browser Tab, you can set your preferred browser and calibrate your browsers.

![Browsers][1]

## Preferred Browser

Select an installed browser from the Preferred Browser dropdown to set that browser as the default test recording and Quick Execution browser.

![Preferred Browser][2]

__Preferred Browser for Responsive Web Test__ option is not applicable for a Visual Studio project. This feature is __only supported in Test Studio Standalone__ application. To find out further details for <a href="https://docs.telerik.com/teststudio/features/testing-types/responsive-test" target="_blank">Responsive web testing</a> you can visit its page in the Test Studio docs site.

## Browser Support Updater

Striving to be up-to-date with the latest browser versions, Test Studio regularly <a href="https://docs.telerik.com/teststudio/prerequisites/configure-your-browser/browser-support-updater" target="_blank">updates the support</a> of any recent changes in browsers' new releases. A notification that there is an update appears, when one is available.

## Extension

Enable/Disable using extension for <a href="/prerequisites/calibrate-browsers#enable-chrome-for-automation" target="_blank">Chrome browser automation</a>.

## Calibrate Browser

The Calibrate Browser section automates the configuration of supported browsers for use with Test Studio. Click **Calibrate** next to a browser to update that browser's settings.

![Calibrate][3]

Confirm that any open instances of this browser will be closed.

![Confirm][4]

To restore the original browser settings that were in place before calibration, click **Restore**.

![Restore][5]

> If your Chrome browser has an active Google Apps session (for example, you are logged into GMail), automatic calibration will not work as expected. To use automatic configuration, log out of your Google account first.

[1]: images/browsers/fig1.png
[2]: images/browsers/fig2.png
[3]: images/browsers/fig3.png
[4]: images/browsers/fig4.png
[5]: images/browsers/fig5.png
