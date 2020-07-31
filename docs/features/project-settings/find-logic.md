---
title: Find Logic (Html) Settings
page_title: Find Logic (Html) for Locating Elements
description: "Test Studio project settings. Reorder the attributes used when building the Find logic for recorded elements in Test Studio recording test. Use custom attributes in the default find logic used to record new elements in Test Studio recording/test."
position: 6
---
# Find Logic (Html)

As elements are added to the **Elements Explorer**, Test Studio uses an intelligent element identification scheme to auto-generate find expressions. When an element is ready to be added to the Elements Explorer, Test Studio tries to use the first item in the list (usually "**id**"). Using this criteria, if the item is unique for the entire page, the element is added, a find expression is created, and Test Studio stops evaluating. As of Test Studio release 2019 R2 Test Studio will also record an <a href="/features/elements-explorer/find-element-by-image" target="_blank">image for each newly recorded element</a>. You can disable it from the <a href="/features/project-settings/element-images" target="_blank">project settings</a>.<br> 

You can **add** new tags to the list, **reorder** them, or **delete** them (except for TextContent and TagIndex which are locked from deletion).

In case the element is not identified with its find expression, Test Studio will use the recorded image as a backup logic. You can enable/disable **Search by image first** to change this order. The configuration here is for the whole project and will be applied for every element, unless it is otherwise specified in the <a href="/general-information/test-execution/test-list-settings" target="_blank">Test List Settings</a> or <a href="/features/test-maintenance/test-step-properties" target="_blank">Test Step Properties</a>.

![Identification Logic][1]

[1]: /img/features/project-settings/find-logic/fig1.png