---
title: Translators for Telerik and Kendo Components
page_title: Built-in Translators for Telerik and Kendo Components
description: "Test Studio Built-In Translators for Telerik and Kendo UI Components. What are the built-in translators? What benefit do I have to use these?  "
position: 7
---

# Test Studio Built-In Translators for Telerik and Kendo UI

Test Studio comes with __dedicated support for the Telerik and Kendo UI components out-of-the-box__. The built-in control types provide methods for invoking actions which are specific to the respective UI component and could otherwise be hard to trigger. Additionally, all Telerik and Kendo UI components have properties exposing the current state and providing easy access to their specific internal structure.

You can read further about the built-in translators in this article.

- [What Are the Built-in Test Studio Translators?](#what-are-the-built-in-test-studio-translators)
- [When Do I Need to Use the Translators?](#when-do-i-need-to-use-the-translators)
- [How Can I Use the Built-in Translators?](#how-can-i-use-the-built-in-translators)
- [Which Telerik and Kendo UI Components are Supported?](#which-telerik-and-kendo-ui-components-are-supported)
- [What Is the Translators Versioning and Which Option Should I Choose?](#what-is-the-translators-versioning-and-which-option-should-i-choose)

## What Are the Built-in Test Studio Translators?

The Test Studio translators are extensions that open a component and expose its properties. This __enables the Test Studio recorder to identify each element__ and provides you with __out-of-the-box action and verification steps__ for that element that you can __add on-the-go, as you record__ your test in the browser.

## When Do I Need to Use the Translators?

Test Studio and its built-in translators facilitate the automation of any application that is built with Telerik and Kendo UI. If __the application you need to automate uses Telerik or Kendo UI components take advantage of the translators__ while you record and execute automated tests that are created with Test Studio.

## How Can I Use the Built-in Translators?

In practice, when you need to record a test for an application that is built with any Telerik or Kendo UI components, you don’t need to do anything different from what you are used to for automating your projects. While you interact with the controls in your application’s UI, __Test Studio recognizes the component under test and lets you add ready-to-use action and verification steps__ instead of generic ones. If you then check these in the test, you can see custom type of steps specific for that component.

Examples are:

* `KendoAngularTab : 'New York City' click action.`
* `TelerikBlazorGridDataCell : Click on Cell [5, 4]`
* `KendoGrid: Grid is currently grouped by 'category.categoryname':`

> __Tip__
><br>
><br>
> Find a detailed how-to guide about <a href="/automated-tests/recording/recording-telerik-kendo-ui-components" target="_blank">recording test scenario for application built with Telerik and Kendo UI</a>.

## Which Telerik and Kendo UI Components are Supported?

Test Studio comes with basic translators for __HTML, Silverlight and WPF__, and exclusively  built translators for __Telerik AJAX and Silverlight components, Telerik UI for Blazor, Kendo UI for Angular and Kendo UI for jQuery__. These translators have a ”base” or ”generic” group of intrinsic translators that are used whenever a more specific translator is not available.

A list of all supported components can be found in the <a href="/features/project-settings/Translators" target="_blank">Project Settings -> Translators</a> dialog. The translators for all components are enabled by default. You can choose to disable a specific translator, or a group of translators, but this is not a recommended practice if not advised otherwise by the Test Studio Support Team.

Test Studio is built with extensibility in mind, so as additional components become available, new translators can be introduced and plugged in. Test Studio is committed to maintaining translators in step with new developments in the Telerik and Kendo UI component libraries, which is why you can expect all translators to always be up-to-date.

## What Is the Translators Versioning and Which Option Should I Choose?

Test Studio supports the __latest available version of the Telerik and Kendo UI components__ following releases through the years and offers __backwards compatibility for previous versions__. This means that you can continue using Test Studio even when an application is no longer in active development mode.

The 2022 releases of the Telerik and Kendo UI components introduced significant changes in their structure and appearance. This brought the need of __versioning for the Test Studio built-in translators__. The available versions and complete detailed mapping regarding which Test Studio release corresponds to what components version can be found in <a href="/features/project-settings/translators#select-the-version-of-the-telerik-components-under-test" target="_blank">this article</a>.

## See Also

* <a href="https://www.telerik.com/blogs/automated-testing-of-kendo-ui-made-easy" target="_blank">Automated Testing for Kendo UI Made Easy</a>.

[1]: /img/features/recorder/translators/fig1.png
[2]: /img/features/recorder/translators/fig2.png
