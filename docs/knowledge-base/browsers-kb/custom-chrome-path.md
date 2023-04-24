---
title: Custom Chrome Path
page_title: Custom Chrome Path
description: How to set Custom Chrome path if the Chrome installation is a custom one. 
position: 1
---
#How to Set a Custom Chrome Path#

Test Studio looks by default at *C:\Program Files (x86)\Google\Chrome\Application\* for the chrome.exe and *C:\Users\\[UserName]\AppData\Local\Google\Chrome\User Data\Default\* for preferences file.

As of version **2015.3.1015** Test Studio also provides options for the user to support **custom location** for Chrome through setting **custom registry keys**.

1.&nbsp; Run **regedit.exe**

2.&nbsp; Navigate to *HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Telerik\TestStudio*

![New Key][1]

3.&nbsp; Create two *String* keys with names **ChromeExePath** and **ChromePreferencesPath** and values respectively: the path to the chrome.exe and the path to the preferences file.

![Custom Registry][2]

Once you set this Test Studio will look for Chrome in the new specified location.

[1]: /img/knowledge-base/browsers-kb/custom-chrome-path/fig1.png
[2]: /img/knowledge-base/browsers-kb/custom-chrome-path/fig2.png
