---
title: Progress® Telerik® Test Studio® Extension Unavailable in Chrome Web Store
description: Provides solutions for executing automated test cases in Edge Chromium or Chrome browser without the 'Progress Telerik Test Studio extension'.
type: troubleshooting
page_title:  Progress® Telerik® Test Studio® Extension is Not Available in Chrome Web Store
tags: progress, telerik, test studio, chrome, extension, edge chromium
res_type: kb
ticketid: 1678431
---


## Description

My web test project is set to execute tests in Edge and Chrome with Progress Telerik Test Studio extension enabled. So, I am trying to execute automated test cases in Edge Chromium (or Chrome) browser using the 'Progress Telerik Test Studio extension' from the Chrome Web Store. However, upon visiting the provided link, it shows that the item is not available. How can I continue execute Test Studio automated tests in Edge Chromium (or Chrome) without the extension?

## Cause

Chrome has officially deprecated Manifest V2 extensions as part of their [extension deprecation timeline](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline). Given that the Test Studio extension is a Manifest V2 extension, it has been affected by this policy change and removed from the Web Store. Consequently, the Edge browser, which utilized the extension from the Chrome Web Store, is also impacted by these changes.

## Solution

To continue using Progress® Telerik® Test Studio® for automated test case execution in Edge Chromium or Chrome without the extension, follow the instructions below:

1. **Switch to Extensionless Browser Mode**: 
- Both Edge Chromium and Chrome support an extensionless mode, which allows for automated testing without the need for the Test Studio extension. This mode was introduced as an alternative due to the anticipated deprecation of Chrome extensions.

2. **Configure the Project to use Edge Chromium and Chrome in Extensionless Mode**:
    - Use the Project Settings and enable the project to use the browsers in their extensionless mode. The setting is a checkbox under the [Browsers tab](https://docs.telerik.com/teststudio/features/project-settings/browsers) which needs to be unchecked.  

3. **Test Execution**:
    - Once you have configured the project in extensionless mode, proceed with your test case execution as usual. This mode is designed to offer a seamless automation testing experience similar to the one with the extension.

4. **Monitoring and Feedback**:
    - Monitor the execution of your automated tests closely to ensure that the transition to extensionless mode does not affect the performance or outcome of your tests.
    - If you encounter any issues or have further questions, consult the Test Studio support documentation or contact the support team for assistance.

By following these steps, you can continue your automated testing efforts in Edge Chromium and Chrome without relying on the 'Progress Telerik Test Studio extension'.


## See Also

- [Configure Your Browser - Edge Chromium](https://docs.telerik.com/teststudio/prerequisites/configure-your-browser/edge-chromium)
- [Chrome Extension Manifest V2 Deprecation Timeline](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline)
