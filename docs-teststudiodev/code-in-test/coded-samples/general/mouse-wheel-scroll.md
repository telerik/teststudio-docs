---
title: Mouse Wheel Scroll
page_title: Mouse Wheel Scroll - Test Studio Dev Documentation
description: Mouse Wheel Scroll
position: 1
---
#Mouse Wheel Scroll#

*I need to invoke desktop mouse scroll actions on an HTML or Silverlight element (typically a scroll bar).*

##Solution##

This is doable with a coded solution. The code is desktop-based, which means it is not associated with an element in your Test Project. Because of this you will need to make sure that the intended target element has focus within the browser before the attempted mouse scroll action. Typically you can give an element focus by invoking a mouse click on it (via regular, non-coded step). Here's an example:

#### __[C#]__

    {{region }}

    Manager.Desktop.Mouse.TurnWheel(100, MouseWheelTurnDirection.Backward);
    {{endregion}}

#### __[VB]__

    {{region }}

    Manager.Desktop.Mouse.TurnWheel(100, MouseWheelTurnDirection.Backward)
    {{endregion}}

