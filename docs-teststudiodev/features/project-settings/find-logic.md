---
title: Smart Find Logic Settings
page_title: Smart Find Logic for Locating Elements | Test Studio Dev Documentation
description: "Set the attributes to be used from Test Studio Dev when generating find expressions while recording tests."
position: 5
---
# Smart Find Logic Tab in Project Settings

Test Studio Dev uses an intelligent element identification algorithm to auto-generate find expressions. It is based on the unique element attributes as ordered in the smart find logic list - the higher an attribute is in the list, the greater priority it has when generating a find expression.

![Identification Logic][1]

When an element is ready to be added to the <a href="/features/elements-explorer/overview" target="_blank">**Elements Explorer**</a>, Test Studio Dev tries to use the first item in the list (usually "id"). Using this criteria, if the item is unique for the entire page, the element is added, a find expression is created, and Test Studio stops evaluating. <br>

You can **add** your custom tags to the find logic list and **reorder** the attributes. You can also remove any unnecessary (except for TextContent and TagIndex which are locked from deletion).

> __Note__ 
> <br>
> <br>
> The list of attributes is applicable for __Html elements__ only.

[1]: images/find-logic/fig1.png