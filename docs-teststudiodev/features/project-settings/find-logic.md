---
title: Find Logic (Html)
page_title: Find Logic (Html) | Test Studio Dev Documentation
description: Modify the attributes to be considered when generating find expression during recording with Test Studio Dev
position: 3
---
# Find Logic Tab in Project Settings

>The list of attributes below is applicable for __html elements__ only.

As elements are added to the <a href="/features/elements-explorer/overview" target="_blank">**Elements Explorer**</a>, Test Studio Dev uses an intelligent element identification scheme to auto-generate find expressions. When an element is ready to be added to the Elements Explorer, Test Studio Dev tries to use the first item in the list (usually "**id**"). Using this criteria, if the item is unique for the entire page, the element is added, a find expression is created, and Test Studio stops evaluating.

You can **add** new tags to the list, **reorder** or **delete** these (except for TextContent and TagIndex which are locked from deletion).

![Identification Logic][1]

[1]: images/find-logic/fig1.png