---
title: Drag & Drop Step
page_title: Drag & Drop Step
description: "Test Studio allows you to record a precise drag and drop step specifying both dragged and target element. Insert an automated Drag&drop action without using code in a Test Studio test. Execute the codeless Drag&drop action from an automated test."
position: 1
---
# Drag and Drop Action

Test Studio supports completely codeless drag&drop action and you can insert such step with only few clicks. 

This type of steps requires two elements - one, which is dragged, and the second to be used as drop target location. Find out how to define these elements in the below article. 

- [Select an element to drag](#select-the-element-to-drag)
- [Pick the target element](#pick-the-target-drop-element)
- [Maintain and adjust Drag&Drop step properties](#maintain-and-edit-the-dragdrop-step)

## Create a Drag&Drop Step

For the purposes of this demonstration we use the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">Kendo jQuery TreeView</a> component, which supports drag and drop. 

### Select the Element to Drag

1.&nbsp; Create a test and start a recording session. Navigate to the mentioned demo page with the TreeView component. 

2.&nbsp; Enable the highlighting and choose an element to drag. Highlight that element and choose the elements menu option to <a href="/features/recorder/highlighting-menu/element-options#build-step" target="_blank">Build Step...</a>.

3.&nbsp; The __Advanced Recording Tools__ window gets opened directly on its __Element Steps__ tab with that element selected in the DOM. Switch to the _Actions_ section and choose the __DragDrop__ action.

![Select Drag & Drop Step][1]

### Pick the Target Drop Element 

4.&nbsp; The __DragDrop__ action step lets you choose the target element where to drop the initially selected element. Click the __Pick__ button under the _Target Element_ property. This switches the focus on the browser and lets you choose the target element with enabled highlighting. Once you stop over an element, a __Select Element__ button appears and you can add this element as target.

![Pick Target Element][2]

5.&nbsp; You can specify the drop point **Location** - you can choose between _Element Center_ or _Specific Point_. __Element Center__ is the default setting, and __Specific Point__ can be <a href="/features/recorder/advanced-recording-tools/element-steps/actions/adv-mouse-actions#specify-the-click-location" target="_blank">set as for the mouse click steps</a>. 

![Element Center Add][3]
 
5.&nbsp; Click the **Add Step** button and the __Drag&Drop__ step is added to the test specifying the two elements you worked with.

![Drag&Drop Step][4]

## Maintain and Edit the Drag&Drop Step

The __Drag&Drop__ step has its specific <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> specifying the two elements used in the step and the offsets used to interact with these. Once a drag and drop step is added into the test you can use its properties to change its behavior completely. 

### Drag Element Properties

The step properties related to the dragged element are named _Drag Element_ and _OffSet_. These define the element to choose on page and the click point to start dragging it. 

![Drag&Drop Step properties][5]

- The <a href="/features/test-maintenance/change-step-target-element" target="_blank">__Drag element__ can be changed with any existing element</a> from the Elements Explorer. 

- The click point __Offset__ for the dragged element can be modified precisely. 

![Drag element offset properties][6]

### Drop Element Properties

The step properties related to the dropped element are named _Drop Element_,  _DropOffSet_ and _DropTargetType_. These define the target element to choose on page and the click point to drop the dragged element.

![Drop element properties][7]

- The <a href="/features/test-maintenance/change-step-target-element" target="_blank">__Drop element__ can be changed with any existing element</a> from the Elements Explorer. 

- The click point __DropOffset__ for the target element can be modified precisely. 

![Drop element offset properties][8]

- The __DropTargetType__ can be _Element_ or _Window_. The more precise option is to use an element as this independent of the size of screen, window, etc. 

![Drop target type properties][9]

If you choose the _Window_ option, you need to consider the size and position of the browser window, which are used to correlate the drop offset location.

![Drop target type window properties][10]


[1]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig6.png
[7]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig7.png
[8]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig8.png
[9]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig9.png
[10]: /img/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop/fig10.png
