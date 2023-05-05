---
title: Refresh DOM tree
page_title: Refresh DOM tree
description: "Trigger manual Refresh of the DOM tree during Test Studio test execution. Is there an option to refresh the DOM tree while test is running."

position: 1
---
# Refresh DOM tree

## Problem

*There are elements against which I could record a step but the execution fails with an element not found exception.*

## Solution

Some elements in an application are loaded in the DOM dynamically during execution - good examples could be drop down menus items, tool tips, etc. This might cause the execution to fail since the dynamic elements are not present in the DOM tree when the page is loaded at first. They appear only after a certain action against the application (hover over, click on the drop down, etc.).

Very often in such situation refreshing the DOM after that particular action will allow the execution to go smoothly. There is no UI step for that though it could be easily obtained in <a href="/features/custom-steps/script-step" target="_blank">a coded step</a>. The only row of code you need to add is the following:

```C#
Manager.ActiveBrowser.RefreshDomTree();
```
```VB
Manager.ActiveBrowser.RefreshDomTree()
```