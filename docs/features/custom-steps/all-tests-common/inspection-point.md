---
title: Inspection Point
page_title: Inspection Point
description: "How can I pause the test execution in Test Studio to inspect the DOM tree at certain moment of the run. Is there a way to verify/check/inspect the DOM tree/the page state at certain step of the test run in Test Studio."
position: 7
---
# Inspection Point

The __Inspection Point__ step pauses the test and displays the DOM Explorer with the current state of the DOM. This is useful for viewing and inspecting the DOM at a specific point in the test.

This article demonstrates how to add this type of step into the test.

Choose the __Inspection Point__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Inspection Point Step][1]

The DOM Explorer gets opened in separate window where you can search through it. The test execution remains paused until you close the DOM Explorer window.

![Inspect Browser DOM Step][2]

[1]: /img/features/custom-steps/inspection-point/step-builder-inspc-point.png
[2]: /img/features/custom-steps/inspection-point/inspect-dom.png

