---
title: Translators for Telerik and Kendo Components
page_title: Built-in Translators for Telerik and Kendo Components
description: "Test Studio Built-In Translators for Telerik and Kendo UI Components. What are the built-in translators? What benefit do I have to use these?  "
position: 7
---

# Test Studio Built-In Translators for Telerik and Kendo UI

Test Studio comes with dedicated support for the Telerik and Kendo UI components out-of-the-box. The built-in control types provide methods for invoking actions which are specific to the respective UI component and could otherwise be hard to trigger. Additionally, all Telerik and Kendo UI components have properties exposing the current state and providing easy access to their specific internal structure.

You can read further about the built-in translators in this article.

## What are the built-in Test Studio translators?

The Test Studio translators are extensions that open a component and expose its properties. This enables the Test Studio recorder to identify each element and provides you with out-of-the-box action and verification steps for that element that you can add on-the-go, as you record your test in the browser.

## When Do I Need to Use the Translators?

Test Studio and its built-in translators facilitate the automation of any application that is built with Telerik and Kendo UI. If the application you need to automate uses Telerik or Kendo UI components take advantage of the translators while you record and execute automated tests that are created with Test Studio.

## How can I use the built-in translators?

In practice, when you need to record a test for an application that is built with any Telerik or Kendo UI components, you don’t need to do anything different from what you are used to for automating your projects. While you interact with the controls in your application’s UI, Test Studio recognizes the component under test and lets you add ready-to-use action and verification steps instead of generic ones. If you then check these in the test, you can see custom type of steps specific for that component.

Examples are:

* `KendoAngularTab : 'New York City' click action.`
* `TelerikBlazorGridDataCell : Click on Cell [5, 4]`
* `KendoGrid: Grid is currently grouped by 'category.categoryname':`

If you enable the element highlight and your mouse hovers over elements while recording, the recording toolbar fans out to indicate more specific translators progressively. It shows enhanced highlighting in the form of colored borders around a "translated" element, indicating how elements are contained within one another. The below example indicates translators for a KendoUI Angular Grid cell.

![Hover mouse over Kendo Grid][1]

The represented menu items are:

* GridDataCell
* GridDataItem
* HtmlTable
* Grid

As the mouse passes over the items in the menu the respective element on page gets highlighted. Select the <a href="/features/verifications/quick-verification" target="_blank">Quick Steps</a> option on the Elements Menu to see the common tasks displayed for the specific element. The screenshot below shows verification and wait steps for a particular grid cell. Without the translator you could not get into that level of detail so easily.

![Click][2]

> __Tip__
><br>
><br>
> Check out this <a href="https://www.telerik.com/videos/teststudio/getting-started-with-using-the-test-studio-translators-for-telerik-ui-for-blazor ">video tutorial</a> which demonstrates how to use the Blazor translators in Test Studio.

## Which Telerik and Kendo UI components are supported?

Test Studio comes with basic translators for HTML, Silverlight and WPF, and exclusively  built translators for Telerik AJAX and Silverlight components, Telerik UI for Blazor, Kendo UI for Angular and Kendo UI for jQuery. These translators have a ”base” or ”generic” group of intrinsic translators that are used whenever a more specific translator is not available.

A list of all supported components can be found in the <a href="/features/project-settings/Translators" target="_blank">Project Settings -> Translators</a> dialog. The translators for all components are enabled by default. You can choose to disable a specific translator, or a group of translators, but this is not a recommended practice if not advised otherwise by the Test Studio Support Team.

Test Studio is built with extensibility in mind, so as additional components become available, new translators can be introduced and plugged in. Test Studio is committed to maintaining translators in step with new developments in the Telerik and Kendo UI component libraries, which is why you can expect all translators to always be up-to-date.

## What is the translators versioning and which option should I choose?

Test Studio supports the latest available version of the Telerik and Kendo UI components following releases through the years and offers backwards compatibility for previous versions. This means that you can continue using Test Studio even when an application is no longer in active development mode.

The 2022 releases of the Telerik and Kendo UI components introduced significant changes in their structure and appearance. This brought the need of versioning for the Test Studio built-in translators. The available versions and complete detailed mapping regarding which Test Studio release corresponds to what components version can be found in <a href="/features/project-settings/translators" target="_blank">this article</a>.

## See Also

* <a href="https://www.telerik.com/blogs/automated-testing-of-kendo-ui-made-easy" target="_blank">__Automated Testing for Kendo UI Made Easy__</a>.

[1]: /img/features/recorder/translators/fig1.png
[2]: /img/features/recorder/translators/fig2.png
