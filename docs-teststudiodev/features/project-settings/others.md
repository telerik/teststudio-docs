---
title: Others
page_title: Others | Test Studio Dev Documentation
description: Miscellaneous settings in Test Studio Dev
position: 6
---
# Others Tab in Project Settings

The Others section provides miscellaneous settings for other specific circumstances.

![Others][1]

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

[1]: images/others/fig1.png
[2]: images/others/fig2.png
