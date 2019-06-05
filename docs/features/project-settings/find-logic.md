---
title: Find Logic (Html)
page_title: Find Logic (Html)
description: "Test Studio project settings. Reorder the attributes used when building the Find logic for recorded elements in Test Studio recording test. Use custom attributes in the default find logic used to record new elements in Test Studio recording/test."
previous_url: /features/project-settings/identification-logic
position: 4
---
# Find Logic (Html)

As elements are added to the **Elements Explorer**, Test Studio uses an intelligent element identification scheme to auto-generate find expressions. When an element is ready to be added to the Elements Explorer, Test Studio tries to use the first item in the list (usually "**id**"). Using this criteria, if the item is unique for the entire page, the element is added, a find expression is created, and Test Studio stops evaluating.<br> 

You can **add** new tags to the list, **reorder** them, or **delete** them (except for TextContent and TagIndex which are locked from deletion).

![Identification Logic][1]

[1]: /img/features/project-settings/find-logic/fig1.png