---
title: Chrome Clean Reinstall
page_title: Chrome Clean Reinstall
description: A clean reinstall of Chrome browser may help to fix Test Studio Chrome Extension not loading or steps not executing issues. A clean reinstall of Chrome ensures the browser's user data is removed.
position: 3
---
# How to Perform Clean Reinstall of Chrome Browser

## Problem

Chrome browser does not start when selected as recording browser, or the test steps are not executed.

## Solution

Clean reinstall of Chrome browser refreshes the standard browser profile and the one used from Test Studio. That way any left over user data which might be interfering and might be preventing the browser to act as expected is cleared. 

The below steps guides you through the process:

1. Start Windows Control Panel > Add/Remove Programs and choose to uninstall Chrome from your machine.

2. In a File Explorer browse to Chrome user data folder - default `C:\Users\\YourUsername\AppData\Local\Google\Chrome`. Delete any leftover data in this folder or remove the complete folder.

3. In a File Explorer browse to Test Studio user data folder for the browsers - `C:\Users\\YourUsername\AppData\Local\ArtOfTest\` and delete the folders for Chrome and Chrome headless profiles: 
    - TSChromeUserData
    - TSChromeHeadlessUserData

4. Perform a fresh install of the latest official version of the Chrome browser.

5. Initiate a test recording session or execution using the Chrome browser.

6. If you continue experience troubles with Chrome test execution, you can contact the Test Studio support team by [submitting a support ticket](/knowledge-base/best-practices-kb/submit-support-ticket) and providing the [Test Studio application log](/knowledge-base/best-practices-kb/generate-application-log#operate-with-logging-in-standalone-version) generated during the attempt to execute or record a test in Test Studio.
