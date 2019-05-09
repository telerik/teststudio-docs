---
title: Custom Chrome Profile
page_title: Custom Chrome Profile
description: Calibrate the default Chrome Profile
position: 2
---
#How to Set a Custom Chrome Profile#

When callibrate automatically Chrome - only the Default profile is calibrated. To change the profile that is calibrated the following actions have to be performed.

As of version **2017.2** Test Studio also provides options for the user to support **custom profile** for Chrome through setting **custom registry keys**.

1.&nbsp; Run **regedit.exe**

2.&nbsp; Navigate to *HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Telerik\TestStudio*

3.&nbsp; Create a *String* key with name **ChromeProfileName** and value - the profile directory as shown on the screenshot below.

> Note that if the **ChromePreferencesPath** is set the variable **ChromeProfileName** would not be taken into consideration.

![Custom Profile][1]

[1]: /img/knowledge-base/browsers-kb/custom-chrome-profile/fig1.png
