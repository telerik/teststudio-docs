---
title: General Project Settings
page_title: General Project Settings
description: "Test Studio project settings - general settings in Test Studio. WPF application default path in Test Studio project.  Https certificate error in Test Studio - register the https connection certificate. Enable tracking of active Test Studio test file - highlight the currently opened test in the Test Studio Project pane."
position: 1
---
# General Project Settings

The General section displays miscellaneous settings for specialized circumstances.

![General][1]

> Check <a href="/features/project-settings/overview" target="_blank">here how to open the **Project Settings** window</a>. 

## Enable Storyboard

By default, screenshots are automatically added to the Storyboard Tab. When this option is unchecked, a placeholder image is used. Uncheck the option when you want to conserve memory and disk space. The Scale slider adjusts the size of the Storyboard Tab between "10%" and "100%".

## WPF

Represents the default application path for WPF tests. Once set, each WPF test will use this path for recording and execution, unless Use default path is unchecked in the <a href="/getting-started/create-test-standalone/wpf-test" target="_blank">WPF test configuration dialog</a>.

## Desktop

Represents the default application path for Desktop tests. Once set, each desktop test will use this path for recording and execution in the <a href="/automated-tests/desktop-testing/desktop-test#use-default-desktop-application-path" target="_blank">Desktop test configuration dialog</a>.

## Connection settings

Use this feature to no longer receive certificate-related warnings when automating your HTTPS web application with Test Studio. See <a href="/knowledge-base/project-configuration-kb/register-certificate" target="_blank">here</a> for more information.

## Web Components

Enable or disable support for <a href="https://developer.mozilla.org/en-US/docs/Web/Web_Components" target="_blank">Web Components</a> in Test Studio recording. It is enabled by default for newly created projects after Test Studio version 2020.1.

## Other Settings

Specific settings related to the use and maintenance of the Test Studio project.

### Track Active File

This property is useful for large projects, which contain multiple tests. If enabled, this will highlight the currently opened and active test file within the Project Explorer.

### Preserve Project State

This property allows you to bring up the project in the same state when it was last closed. If enabled, by next launch of the project, any tests and code files not closed, will be automatically opened.

## SL Connect Timeout

The amount of time in milliseconds to wait for Test Studio to connect to a Silverlight application.

[1]: /img/features/project-settings/general/fig1.png
