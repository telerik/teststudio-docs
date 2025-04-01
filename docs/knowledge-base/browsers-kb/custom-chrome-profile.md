---
title: Custom Chrome Profile
page_title: Custom Chrome Profile
description: Calibrate the default Chrome Profile
position: 2
---
## How to Set a Custom Chrome Profile

Test Studio allows you to create a custom profile in Chrome browser, which remains in use only when running tests from Test Studio.

Follow the below steps to create and calibrate a custom profile.

1.&nbsp; Start the __Windows Registry Editor__.
    You can type _Registry Editor_ in the Start menu or use the  _Run..._ option and type *regedit.exe*.

2.&nbsp; Navigate to node *HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Telerik\TestStudio*

3.&nbsp; Create a key of type *String* and name it **ChromeProfileName**

> **Note**
> <br>
> <br>
> If you have set the registry keys for <a href="/knowledge-base/browsers-kb/custom-chrome-path" target="_blank">using Chrome from custom installation path</a>, the __custom profile registry key is not taken__ into account.

4.&nbsp; Modify the value of that key and set a new profile name - _testingProfile_, for example.

![Custom Edge Profile][1]

5.&nbsp; Start a Test Studio project and open a web test. Trigger a recording session choosing the Chrome browser, but __uncheck the checkbox for browser calibration__ for this first run - it is only required to actually create the new profile.

6.&nbsp; Once the browser starts you see the Test Studio screen reporting "Waiting for extension 30 sec...". The __extension is not installed in this profile__ of the browser, so after the 30 seconds timeout, you get a link to the extension - open it and add the <a href="https://chrome.google.com/webstore/detail/progress-telerik-test-stu/gegcllkonmciadpdldechnepmjildoan" target="_blank">Progress Telerik Test Studio extension</a>.  

7.&nbsp; Stop that first recording session by closing the browser instance.

8.&nbsp; Open the <a href="/automated-tests/test-execution/quick-run-browsers#calibrate-browsers" target="_blank">browser calibration window and now calibrate the Chrome browser.

9.&nbsp; As long as that registry key exists, Test Studio will use it to start the Chrome browser for running and recording tests.

[1]: /img/knowledge-base/browsers-kb/custom-chrome-profile/fig1.png
