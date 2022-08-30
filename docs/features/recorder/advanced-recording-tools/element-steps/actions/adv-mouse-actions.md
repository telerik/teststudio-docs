---
title: Mouse Click on Specified Location
page_title: Mouse Click on Specified Location
description: "Test Studio allows you to specify the coordinates of the mouse click correalted to the target element. Add mouse click actions into the test to handle any type of automation test scenarios as if a real user would handle these. "
position: 0
---
# Mouse Click on Specified Location

The __Advanced Mouse Actions__ section allows you to modify the coordinates of the click step and specify where to send the click. 

Check the advanced options for the different click steps. 

## Advanced Mouse Click Options

When building a mouse click step from the __Advanced Recording Tools__ window you have the option to choose the **Location** of the click. You can choose between _Element Center_ or _Specific Location_. The __Element Center is the default value__ and alls steps added through the highlighting menu are set to click in the absolute center of the target element.

![Add Mouse Action Step][1]

> __Tip__
>
> The <a href="/features/test-maintenance/test-step-properties" target="_blank">Step Properties</a> for the mouse click steps 

 sections to help you add the right step and with the right configurations. That said, you can adjust the location and other properties from the <a href="/features/test-maintenance/test-step-properties" target="_blank">Step Properties</a> pane in Test Studio later. 

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

[1]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig4.png
