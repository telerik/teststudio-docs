---
title: What is Browser Calibration
page_title: What is Browser Calibration
description: "Configure the supported browsers to use these for testing with Test Studio. Prerequisites for testing web applications."
position: 0
---

# What is Browser Calibration

A specific set of settings is required to prepare a browser for the recording and execution of tests with Test Studio. Some of the browsers also require an extension to be added.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

To ease you in applying these settings, Test Studio provides a built-in approach to <a href="/features/project-settings/browsers" target="_blank">calibrate all supported browsers</a>. Follow the links below for more calibration details about each supported browser and a download link to the particular extension:

- <a href="/prerequisites/configure-your-browser/chrome" target="_blank">Google Chrome</a>
- <a href="/prerequisites/configure-your-browser/edge-chromium" target="_blank">MS Edge (Chromium based)</a>
- <a href="/prerequisites/configure-your-browser/firefox" target="_blank">Mozilla Firefox</a>
- <a href="/prerequisites/configure-your-browser/internet-explorer" target="_blank">Internet Explorer</a>
- <a href="/prerequisites/configure-your-browser/edge" target="_blank">MS Edge (Legacy)</a>
- <a href="/prerequisites/configure-your-browser/edge" target="_blank">Safari</a>

## Accept Extension Permission for Version 2020.2.728

The latest 2020 R2 Test Studio release (v.2020.2.804) introduces the <a href="/features/testing-types/responsive-test" target="_blank">web responsive testing feature</a>. With this release, Test Studio published a corresponding version of the extensions for Chrome, Edge Chromium and Firefox. The latest version of the extension (v.2020.2.728.1) requires additional permissions; therefore, it gets disabled after the update. 

To re-enable it, you need to __manually accept the permissions request for each browser and machine__. When you open the browser, there is a warning sign on the _Settings_ menu.

![Settings menu disabled extension][1]

Open the _Settings_ menu and click on the message that the Test Studio extension is disabled.

![Extension is disabled message][2]

Click the notification message and a Popup appears to confirm if you accept the requested permissions and re-enable the Test Studio extension.

![Accept permissions][3]

[1]: /img/prerequisites/browser-config/edge-notification.jpg
[2]: /img/prerequisites/browser-config/accept-popup.jpg
[3]: /img/prerequisites/browser-config/accept-permissions.jpg
