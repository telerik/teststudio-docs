---
title: Drag&Drop
page_title: Drag&Drop | Test Studio Dev Documentation
description: Drag&Drop could be simulated by Test Studio Dev
slug: mouse-actions/drag-drop
position: 0
---
# Drag and Drop

1.&nbsp; Start <a href="/getting-started/test-recording/overview" target="_blank">recording a test</a>.

2.&nbsp; Enable Hover Over Highlighting from the Recording Toolbar. When the mouse pauses over a highlighted element in the recording surface the context menu with multiple options.

3.&nbsp; Highlight an element you want to drag and drop and click **Build Step**.

![Build Step](images/build-step.png)

4.&nbsp; From Mouse Actions select **DragDrop** and click **Pick** button.

![Pick Target Element](images/pick-target.png)

5.&nbsp; Highlight and select the target element where you want to drop the element.

![Select Target](images/select-target.png)

6.&nbsp; Choose **Element Center** from the **Location** drop down to drop the element in the center of the target element and click **Add Step**. The Drag&Drop step is created in Test Studio.

![Add Step](images/add-step.png)

## Drag and Drop to a specific location

Choose **Specific Point** from the **Location** drop down to specify the exact coordinates where to drop the element. 

![Specific Point](images/specific-point.png)

Select against which part of the target element will be the specific point calculated from the grid.

![Specific coordinates](images/specific-coordinates.png)

Drag the circle to the point where you want to drop the element (the coordinates will be calculated automatically against the selected element) or type the coordinates manually.

![Select Drop Point](images/select-point.png)

Click **Add Step**. The Drag&Drop step is created in Test Studio.
