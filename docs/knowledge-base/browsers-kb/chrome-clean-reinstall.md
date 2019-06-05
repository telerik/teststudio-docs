---
title: Chrome Clean Reinstall
page_title: Chrome Clean Reinstall
description: Fix Test Studio Chrome Extension not loading or steps not executing. Reinstall Chrome browser and ensure that user data is removed.
position: 3
---
#How to Reinstall Chrome Browser and Clean User Data#

##Problem

Test Studio extension in Chrome browser does not load during recording, or the test steps are not executing.

##Solution

Ensure that Chrome browser does not have any unnecessary user data left over. Follow the steps below to reinstall the browser remove its "User Data" folder.

1. Uninstall Chrome completely from your machine

2. Navigate to *C:\Users\<YousUsername>\AppData\Local\Google\Chrome* and delete any leftover data in this folder

3. Perform a fresh install of the latest offical version of Chrome browser.

4. [Calibrate the browser](https://docs.telerik.com/teststudio/getting-started/configure-your-browser/chrome#2-browser-calibration) and install the [Telerik Test Studio extension](https://chrome.google.com/webstore/detail/progress-telerik-test-stu/gegcllkonmciadpdldechnepmjildoan).