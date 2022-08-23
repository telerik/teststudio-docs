---
title: Quick Mouse Actions
page_title: Quick Mouse Actions
description: "Add mouse action steps from the Highlighting menu while recording Test Studio tests. Choose among left single or double mouse click, right mouse click. Add a mouse step to hover over an element."
position: 0
---
# Quick Mouse Actions

The __Quick Mouse Actions__ section in the Highlighting menu allows you to add different type of desktop mouse actions like right or double clicks and hover over an element.

![Add Quick Mouse Action Step][1]

## General Notes



re are different types of mouse actions that you can record against specific element in the application under test. Some are basic, like Left or Right click, and some are more complex like HoverOver and Drag&Drop. All of them behave as if the real user performs those actions by sending desktop mouse commands. 

Each step comes with a **Description** and **Location** sections to help you add the right step and with the right configurations. That said, you can adjust the location and other properties from the <a href="/features/test-maintenance/test-step-properties" target="_blank">Step Properties</a> pane in Test Studio later. 

> **Note**
>
> The only exception is the <a href="/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop" target="_blank">Drag&Drop</a> step, which need a target element instead of location. 

1.&nbsp;Select an element from the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a>.

2.&nbsp;Choose the mouse action you want to add.

3.&nbsp;Configure the location.

4.&nbsp;Click **Add Step** button. New "Desktop command" step is created in your test.

![Add Mouse Action Step][1]

## Specific Location

Configure where exactly you want the mouse action to be executed.

1.&nbsp;Choose **Specific Point** from the **Location** drop down.

![Specify Location][2]

2.&nbsp;Select a starting point from the grid. The coordinates will be calculated from that point.

![Starting Point][3]

3.&nbsp;Drag the circle to the exact location, where you want to click, or type the coordinates manually.

![Starting Point][4]

4.&nbsp;Click **Add Step**. New "Desktop command" step with the specified coordinates is created in your test.

[1]: /img/features/recorder/highlighting-menu/mouse-actions/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig4.png