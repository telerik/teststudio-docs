---
title: Invoke Mouse Hover
page_title: Invoke Mouse Hover
description: Insert Mouse Hoverover step. I recorded a click in a fly-out sub-menu, however it does not execute properly because the menu never properly expands to expose the element. Invoke mouse action.
position: 1
---
## Invoke a Mouse Hover event

## PROBLEM

I recorded a click in a fly-out sub-menu, however it does not execute properly because the menu never properly expands to expose the element.

## SOLUTION

Invoking a mouse action can come in handy, especially in navigation menus that use hover-over fly-out sub-menus.

1.&nbsp; To get started, select the hover-over highlighting tool from the recorder toolbar which is docked to the browser.

2.&nbsp; Next, select the element on which you would like to invoke the hover-over mouse-action on, stay hovered.

3.&nbsp; The Element Menu is now displayed. Note the icons highlighting below; these are used to invoke **Javascript Events** and **Mouse Actions**.

4.&nbsp; Select **Mouse Actions**.

5.&nbsp; Select **Mouse Hover** by double-clicking it.

![Mouse actions][1]

6.&nbsp; A desktop command is added to your test. It invokes a mouse hover-over action triggering the menu to fly out. This allows you to select a sub-menu item.
 
7.&nbsp; Please note that desktop commands may not function correctly if focus is removed from the execution browser.

[1]: /img/knowledge-base/test-automation-kb/invoke-mouse-hover/fig1.png
