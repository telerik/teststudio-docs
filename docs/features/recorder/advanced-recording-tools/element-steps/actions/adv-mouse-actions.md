---
title: Mouse Click Actions
page_title: Advanced Mouse Click Actions
description: "Test Studio allows you to specify the coordinates of the mouse click correalted to the target element. Add mouse click actions into the test to handle any type of automation test scenarios as if a real user would handle these. "
position: 0
---
# Advanced Mouse Click Actions

The __Advanced Mouse Actions__ section allows you to modify the coordinates of the click step and specify where to send the click. 

Check the advanced options for the different click steps. 

## Mouse Click Options

When building a mouse click step from the __Advanced Recording Tools__ window you have the option to choose the **Location** of the click. You can choose between _Element Center_ or _Specific Point_. __Element Center is the default setting__ and all steps added through the highlighting menu are set to click in the absolute center of the target element.

![Add Mouse Action Step][1]

> __Tip__
>
> Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the desktop action step and allow you to change the command type or offset position of the click point. 
> 
> ![Step Properties][0]

## Specify the Click Location

When building a mouse click step from the __Advanced Recording Tools__ window you can set the **Location** of the action to _Specific Point_. Then you see the additional settings for _Specific Point Coordinates_ on screen. 

![Specify Location][2]

The default starting point for calculating the coordinates of the click is the _Element Center_. You can change that starting point horizontally to top, center, bottom and vertically to left, center and right. 

![Starting Point][3]

Drag the circle to the exact location, where you want to send the click and see the coordinates changing as you move it. You can type the coordinates manually into the _X_ and _Y_ fields.

![Adjust Click Point][4]

When the coordinates are adjusted, click the **Add Step** button to insert the step into the test. 

> __Tip__
>
> The specific <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> reflect the adjustments for the offset position of the click point.
> 
> ![Adjusted Click Point step properties][5]



[0]: /img/features/recorder/highlighting-menu/mouse-actions/fig3.png

[1]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions/fig5.png
