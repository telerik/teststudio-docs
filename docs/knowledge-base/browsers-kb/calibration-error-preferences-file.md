---
title: Edge Calibration Error
page_title: Edge Calibration Error
description: "Edge Calibration Error in Test Studio - Could not read Edge Preferences file Error during serialization or deserialization. The length of the string exceeds the value set on the maxJsonLength value." 
position: 1
---
## Error on Trying to Calibrate Edge Browser 

Test Studio <a href="/prerequisites/configure-your-browser/browser-configuration" target="_blank">browsers calibration</a> is a mandatory step to set the supported browsers in compatible state for recording and execution of automated tests.

Due to the specifics of how Edge browser works and stores user data you might face troubles when trying to calibrate it. This article describes how to deal with the _'Could not read Edge Preferences file'_ error.

## Preferences File Error when Calibrating Edge

I am trying to calibrate Edge browser from Test Studio Project Settings and I get the following error:

`Could not read Edge Preferences file Error during serialization or deserialization using the JSON JavaScriptSerializer. The length of the string exceeds the value set on the maxJsonLength value. Parameter name: input.
`
![Calibrating Edge Preferences File Error](/img/knowledge-base/browsers-kb/calibration-error-preferences-file/fig1.png)

## How to Solve the Error and Calibrate the Browser?

When using Edge for browsing the Internet, it stores its form fill data into the file  __"C:\Users\\[current-username]\AppData\Local\Microsoft\Edge\User Data\Default\Preferences"__. As a result it grows in size with each next page visited.

Test Studio calibration settings use this same Preferences file, but there is a limit for the length of JSON string that can be handled. Thus, when Edge is used for everyday browsing, its Preferences file gets larger than the Test Studio limitations for reading it and this brings the error upon calibration.

## Solution 1

Ensure to use <a href="/prerequisites/configure-your-browser/edge-chromium#using-extension-for-edge-chromium-automation-optional" target="_blank">Edge browser in the mode without extension</a> and skip the calibration step from Project Settings. The calibration for the extension-less mode of the browsers is automatically applied before test run.

## Solution 2

Delete the current Edge profile and recreate it. This can be accomplished by following the below step:

1. Close all Edge browser instances.

2. Delete folder __"C:\Users\\[current-username]\AppData\Local\Microsoft\Edge\User Data\Default"__.

3. Start Edge.

4. Open Test Studio and calibrate the Edge browser.
