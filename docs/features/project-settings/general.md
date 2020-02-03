---
title: General Project Settings
page_title: General
description: "Test Studio project settings - general settings in Test Studio. WPF application default path in Test Studio project. Highlighting border adjustment in Test Studio recording. Https certificate error in Test Studio - register the https connection certificate. Enable tracking of active Test Studio test file - highlight the currently opened test in the Test Studio Project pane."
position: 1
---
# General

The General section displays miscellaneous settings for specialized circumstances.

![General][1]

## Highlighting

The "Automation Overlay Surface" defines the highlight border color, border width and the amount of time before the Elements Menu displays.<br>

Click the **Border button** to display a color selector and use the sliders to adjust **Highlight Border Width** and **Menu Hold Time**. Delaying the Elements Menu display can be helpful if you're trying to hover the mouse and the Elements Menu is popping up too quickly.

![Highlighting][2]

## WPF

Represents the default application path for WPF tests. Once set, each test will use this path for recording and execution, unless Use default path is unchecked in the <a href="/getting-started/create-test-standalone/wpf-test" target="_blank">WPF test configuration dialog</a>.

## Connection settings

Use this feature to no longer receive certificate-related warnings when automating your HTTPS web application with Test Studio. See <a href="/knowledge-base/project-configuration-kb/register-certificate" target="_blank">here</a> for more information.

## Http Proxy

This property allows the user to specify whether to <a href="/advanced-topics/coded-samples/general/using-the-http-proxy" target="_blank">use the HTTP proxy</a> in Quick Execution.

## Track Active File

This property is useful for large projects, which contain multiple tests. If enabled, this will highlight the currently opened and active test file within the Project Explorer.

[1]: /img/features/project-settings/general/fig1.png
[2]: /img/features/project-settings/general/fig2.png
