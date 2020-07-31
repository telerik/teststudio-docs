---
title: Browsers Configuration Settings
page_title: Browsers Configuration Settings
description: "Test Studio project settings. Browser specific settings in Test Studio. Configure browsers in Test Studio. Calibrate Browsers in Test Studio. Set Preferred browser for recording and execution"
position: 4
---
# Browsers

Under the Browser Tab, you can set your preferred browser, check if the dialog handlers are up-to-date and calibrate your browsers.

![Browsers][1]

## Preferred Browser

Select an installed browser from the _Preferred Browser_ section to set it as the default test recording and quick execution browser for web tests and responsive web tests (responsive web tests support only Chrome and Edge Chromium).

![Preferred Browser][2]

> As of version **R1 2016** the **Preferred browser** can be directly selected from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Web ribbon</a>.

## Dialog Handlers

Striving to be up-to-date with the latest browser versions, Test Studio needs to regularly update the dialog handlers, if any of the supported browsers release differences in their structure. When this is necessary, you will see a notification that there is an update available.

![Dialog Handler Update][3]

## Calibration

The Calibrate Browser section automates the configuration of supported browsers for use with Test Studio. Click **Calibrate** next to a browser to update that browser's settings. Confirm that any open instances of this browser will be closed.

![Confirm][4]

To restore the original browser settings that were in place before calibration, click **Restore**.

![Restore][5]

> __Note!__ You cannot restore settings that were calibrated by a version of Test Studio before 2013 R2. <br><br>
> __Note!__ If your Chrome browser has an active Google Apps session (for example, you are logged into GMail), automatic calibration will not work as expected. To use automatic configuration, log out of your Google account first.

[1]: /img/features/project-settings/browsers/fig1.png
[2]: /img/features/project-settings/browsers/fig2.png
[3]: /img/features/project-settings/browsers/fig3.png
[4]: /img/features/project-settings/browsers/fig4.png
[5]: /img/features/project-settings/browsers/fig5.png
