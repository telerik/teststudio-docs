---
title: Chrome Clean Reinstall
page_title: Chrome Clean Reinstall
description: A clean reinstall of Chrome browser may help to fix Test Studio Chrome Extension not loading or steps not executing issues. A clean reinstall of Chrome ensures the browser's user data is removed.
position: 3
---
# How to Perform Clean Reinstall of Chrome Browser

## Problem

Test Studio extension in Chrome browser does not load during recording, or the test steps are not executing.

## Solution

Complete a clean reinstall of Chrome browser to ensure left over user data interferes with the Test Studio extension and prevents the browser to act as expected. The below steps guides you through the process:

1. Start Windows Control Panel > Add/Remove Programs and choose to uninstall Chrome from your machine.

2. In a File Explorer browse to Chrome user data folder - default is *C:\Users\\\<YourUsername>\AppData\Local\Google\Chrome*. Delete any leftover data in this folder or remove the complete folder.

3. In a File Explorer browse to Test Studio user data folder for the browsers - *C:\Users\\\<YourUsername>\AppData\Local\ArtOfTest\* and delete the folders for Chrome and Chrome headless profiles: 
    - TSChromeUserData
    - TSChromeHeadlessUserData

4. Perform a fresh install of the latest official version of the Chrome browser.

5. Initiate a test recording session or execution using the Chrome browser.

6. If you continue experience troubles with Chrome test execution, you can contact the Test Studio support team by [submitting a support ticket](/knowledge-base/best-practices-kb/submit-support-ticket).
