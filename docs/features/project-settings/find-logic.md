---
title: Smart Find Logic Settings
page_title: Smart Find Logic for Locating Elements
description: "Test Studio project settings. Reorder the attributes used when building the Find expressions for elements recorded in Test Studio test. Use custom elements' attributes in the default find logic used to record new elements in Test Studio tests."
position: 6
---
# Smart Find Logic

Test Studio uses an intelligent element identification algorithm to auto-generate find expressions. It is based on the unique element attributes as ordered in the smart find logic list - the higher an attribute is in the list, the greater priority it has when generating a find expression.

![Identification Logic][1]

When an element is ready to be added to the Elements Explorer, Test Studio tries to use the first item in the list (usually "**id**"). Using this criteria, if the item is unique for the entire page, the element is added, a find expression is created, and Test Studio stops evaluating. <br>

You can **add** your custom tags to the find logic list and **reorder** the attributes. You can also remove any unnecessary (except for TextContent and TagIndex which are locked from deletion).

## Element Images

As of Test Studio release 2019 R2 Test Studio also records an <a href="/features/elements-explorer/find-element-by-image" target="_blank">image for each newly added element</a>. In case an element is not identified with its find expression, Test Studio falls back to use the recorded image as a backup image search logic. You can find additional setting for using the element images in the <a href="/features/project-settings/element-images" target="_blank">Element Images tab</a> in Project Settings.

[1]: /img/features/project-settings/find-logic/fig1.png