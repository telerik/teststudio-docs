---
title: Mouse Wheel Scroll
page_title: Mouse Wheel Scroll
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Mouse Wheel Scroll#

*I need to invoke desktop mouse scroll actions on an HTML or Silverlight element (typically a scroll bar).*

##Solution##

This is doable with a coded solution. The code is desktop-based, which means it is not associated with an element in your Test Project. Because of this you will need to make sure that the intended target element has focus within the browser before the attempted mouse scroll action. Typically you can give an element focus by invoking a mouse click on it (via regular, non-coded step). Here's an example:

```C#
Manager.Desktop.Mouse.TurnWheel(100, MouseWheelTurnDirection.Backward);
```
```VB
Manager.Desktop.Mouse.TurnWheel(100, MouseWheelTurnDirection.Backward)
```
