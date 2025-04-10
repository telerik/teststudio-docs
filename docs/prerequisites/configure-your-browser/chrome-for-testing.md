---
title: Chrome for Testing
page_title: Configure Chrome for Testing for Test Studio Automation
description: "Configure Chrome for testing to use for testing with Test Studio. Prerequisites for testing against Chrome with Test Studio. Install Chrome extension for Test Studio testing."
position: 4
---

# Configure Chrome for Testing for Test Studio Automation 

The document describes the steps to enable Test Studio to use Chrome for Testing browser for test recording and execution.

Chrome is one of the supported from Test Studio browsers for automation of web applications. Since Chrome officially announced their <a href="https://developer.chrome.com/blog/chrome-for-testing" target="_blank">Chrome for Testing flavor channel</a>, Test Studio included support also for it. 

Use the below steps to switch using the Chrome for Testing browser for test recording and execution in Test Studio.  

## Install Chrome for Testing

1. Go to the official Chrome channel to download Chrome for Testing setup - https://googlechromelabs.github.io/chrome-for-testing/#stable
2. Look for the URL of the current `win64` or `win32` stable version and select the one which corresponds to the OS in use.
    For example: https://storage.googleapis.com/chrome-for-testing-public/132.0.6834.159/win64/chrome-win64.zip
3. Download the zip file by pasting the URL in the browser and note the download folder.
4. Open a File Explorer and browse to `Program Files` or `Program Files x86` depending on the OS in use.
5. Create the following folder: Google\Chrome for Testing\Application
6. Copy the downloaded zip file to this folder and extract it.
7. Run the `setup.exe` in the same folder.

## Setup Test Studio to use Chrome for Testing

Once the Chrome for Testing setup is complete Test Studio starts using it automatically and no further adjustment is needed.