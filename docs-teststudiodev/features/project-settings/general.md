---
title: General Project Settings
page_title: General Project Settings | Test Studio Dev Documentation
description: "Miscellaneous settings in Test Studio Dev"
position: 1
---
# General Tab in Project Settings

The General section provides miscellaneous settings for other specific circumstances.

![general][1]

## Enable Storyboard

By default, screenshots are automatically added to the Storyboard Tab. When this option is unchecked, a placeholder image is used. Uncheck the option when you want to conserve memory and disk space. The Scale slider adjusts the size of the Storyboard Tab between "10%" and "100%".

## WPF

Represents the default application path for WPF tests. Once set, each test will use this path for recording and execution, unless _Use default_ path is unchecked in the <a href="/features/recorder/record-test#record-a-wpf-test" target="_blank">WPF test configuration dialog</a>.

## Desktop

Represents the default application path for Desktop tests. Once set, each desktop test will use this path for recording and execution in the <a href="/features/recorder/record-test#record-a-desktop-test" target="_blank">Desktop test configuration dialog</a>.

## Connection Settings

Use this feature to no longer receive certificate-related warnings when automating your HTTPS web application with Test Studio Dev. See <a href="/advanced-topics/project-configuration/register-certificate" target="_blank">to register the Fiddler certificate</a> for more information.

## Web Components

Enable or disable support for <a href="https://developer.mozilla.org/en-US/docs/Web/Web_Components" target="_blank">Web Components</a> in Test Studio recording. It is enabled by default for newly created projects after Test Studio version 2020.1.

## Other Settings

Specific settings related to the use and maintenance of the Test Studio project.

## Track Active File

This property is useful for large projects, which contain multiple tests. If enabled, this will highlight the currently opened and active test file within the Project Explorer.

### Preserve Project State

This property allows you to bring up the project in the same state when it was last closed. If enabled, by next launch of the project, any tests and code files not closed, will be automatically opened.

## SL Connect Timeout

The amount of time in milliseconds to wait for Test Studio to connect to a Silverlight application.

[1]: images/general/fig1.png

