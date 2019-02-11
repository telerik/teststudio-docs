---
title: General
page_title: General | Test Studio Dev Documentation
description: Miscellaneous settings in Test Studio Dev
position: 1
---
# general Tab in Project Settings

The General section provides miscellaneous settings for other specific circumstances.

![general][1]

## Highlighting

The "Automation Overlay Surface" defines the highlight border color, border width and the amount of time before the Elements Menu displays.

Click the **Border button** to display a color selector and use the sliders to adjust **Highlight Border Width** and **Menu Hold Time**. Delaying the Elements Menu display can be helpful if you're trying to hover the mouse and the Elements Menu is popping up too quickly.

![Highlighting][2]

## WPF

Represents the default application path for WPF tests. Once set, each test will use this path for recording and execution, unless _Use default_ path is unchecked in the WPF test configuration dialog.

## Connection settings

Use this feature to no longer receive certificate-related warnings when automating your HTTPS web application with Test Studio Dev. See <a href="/advanced-topics/project-configuration/register-certificate" target="_blank">to register the Fiddler certificate</a> for more information.

## Http Proxy

This property allows the user to specify whether to use the HTTP proxy in Quick Execution.

## Track Active File

This property is useful for large projects, which contain multiple tests. If enabled, this will highlight the currently opened and active test file within the Project Explorer.

[1]: images/general/fig1.png
[2]: images/general/fig2.png
