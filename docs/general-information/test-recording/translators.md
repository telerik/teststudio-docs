---
title: Translators
page_title: Translators
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/recording-tests/translators.aspx, /user-guide/recording-tests/translators
position: 1
---
#Translators#

The party that best understands the internals of a component is the party that built it. The Telerik extensibility model allows third party web component vendors to encapsulate deep knowledge of component internals to share with their customers.

* Translators are extensions that open up an element to work with Test Studio.
* A translator describes the actions of an element that can be automated and verifications that can be performed.
* Translators allow interaction with the Test Studio user interface including the <a href="/features/elements-menu/overview" target="_blank">Elements Menu</a> and <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.
* Test Studio ships with basic translators for HTML, Silverlight and WPF, and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular.
* Test Studio was built with extensibility in mind, so as additional controls become available, new translators can be plugged in.
* Telerik is committed to maintaining translators in step with Telerik controls changes, so you can expect the translators to always be up-to-date.

As your mouse hovers over elements during the recording, the recording toolbar will fan out to indicate progressively more specific translators.

![Hover][1]

It shows enhanced highlighting in the form of colored borders around a "translated" element, indicating how elements are contained within one another. The translators for a KendoUI Angular Grid cell are shown in this example. The menu items represent:

* GridDataCell
* GridDataItem
* HtmlTable
* Grid

As the mouse passes over the items in the menu the respective element on page will be highlighted. Select the <a href="/features/verifications/quick-verification" target="_blank">Quick Steps</a> option on the Elements Menu. Common tasks are displayed for the specific element. The screenshot below shows verification and wait tasks for a particular grid cell. Without the translator you could not get to this level of detail easily.

![Click][2]

Test Studio comes with translators for HTML, Silverlight, and WPF and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular. These translators have a "base" or "generic" group of intrinsic translators that are used whenever a more specific translator is not available. These translators are listed in the <a href="/features/project-settings/Translators" target="_blank">Project Settings</a> dialog.

[1]: /img/general-information/test-recording/translators/fig1.png
[2]: /img/general-information/test-recording/translators/fig2.png