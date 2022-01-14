---
title: Translators
page_title: Translators
description: "Test Studio translators for the Telerik controls. "
position: 7
---
# Translators #

The party that best understands the internals of a component is the party that built it. The Telerik extensibility model allows third party web component vendors to encapsulate deep knowledge of component internals to share with their customers.

* Translators are extensions that open up an element to work with Test Studio.
* A translator describes the actions of an element that can be automated and verifications that can be performed.
* Translators allow interaction with the Test Studio user interface including the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Elements Menu</a> and <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.
* Test Studio ships with basic translators for HTML, Silverlight and WPF, and translators built specifically for __Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular, Blazor__.
* Test Studio was built with extensibility in mind, so as additional controls become available, new translators can be plugged in.
* Telerik is committed to maintaining translators in step with Telerik controls changes, so you can expect the translators to always be up-to-date.

> __Tip__
><br>
><br>
> Check out this <a href="https://www.youtube.com/watch?v=hCEoohdp00M&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=2">video tutorial</a> which demonstrates how to use the Blazor translators in Test Studio.

As your mouse hovers over elements during the recording, the recording toolbar will fan out to indicate progressively more specific translators.

![Hover][1]

It shows enhanced highlighting in the form of colored borders around a "translated" element, indicating how elements are contained within one another. The translators for a KendoUI Angular Grid cell are shown in this example. The menu items represent:

* GridDataCell
* GridDataItem
* HtmlTable
* Grid

As the mouse passes over the items in the menu the respective element on page will be highlighted. Select the <a href="/features/verifications/quick-verification" target="_blank">Quick Steps</a> option on the Elements Menu. Common tasks are displayed for the specific element. The screenshot below shows verification and wait tasks for a particular grid cell. Without the translator you could not get to this level of detail easily.

![Click][2]

Test Studio comes with translators for HTML, Silverlight, and WPF and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular, Blazor. These translators have a "base" or "generic" group of intrinsic translators that are used whenever a more specific translator is not available. These translators are listed in the <a href="/features/project-settings/Translators" target="_blank">Project Settings</a> dialog.

__See Also:__ You can find additional information on Kendo Translators in our blog post <a href="https://www.telerik.com/blogs/automated-testing-of-kendo-ui-made-easy" target="_blank">__Automated Testing for Kendo UI Made Easy__</a>.

[1]: /img/features/recorder/translators/fig1.png
[2]: /img/features/recorder/translators/fig2.png
