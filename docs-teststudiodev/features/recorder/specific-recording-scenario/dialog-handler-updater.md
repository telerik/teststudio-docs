---
title: Dialog Handler Updater
page_title: Dialog Handler Updater | Test Studio Dev Documentation
description: How to update the Dialog Handlers.
slug: features/dialogs
position: 0
---
# Dialog Handler Updater

Browsers are constantly evolving. They come with a couple of official releases per year and few more updates. Some of these updates are changing the UI structure of the whole browser. This, on other hand, is impacting how Test Studio Dev handles the dialog and notification windows.

Hence, after such breaking changes introduced by the browsers, Test Studio Dev should be updated accordingly. This is managed with the __Dialog handler update__ functionality. If you are using the latest official release of Test Studio Dev, and there is a browser update which somehow is affecting the tool normal operation, a notification for __Dialog handler update__ will  be shown in the _Browsers_ section in the _Project Settings_ window.

![Handler Update Notification][1]

For an immediate update of the Dialog handler configurations, open the <a href="/features/project-settings/overview" target="_blank">_Project Settings_</a> window to its _Browsers_ section. Click _Update_ button next to ___Dialog Handler update available___ notification.

![Handler Update Button][2]

Once the update is successfully installed you need to restart Test Studio in order the changes to take effect.

![Restart Required][3]

[1]: images/dialog-handler-updater/fig1.png
[2]: images/dialog-handler-updater/fig2.png
[3]: images/dialog-handler-updater/fig3.png
