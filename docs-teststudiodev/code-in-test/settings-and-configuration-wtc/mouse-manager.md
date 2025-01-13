---
title: Mouse Manager
page_title: Mouse Manager
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Mouse Manager Class

The Mouse manager class is used to simulate moving the physical mouse and performing various types of mouse clicks. It has the following properties:

<table class="docs">
<tr>
	<th>Property</th><th>Brief Description</th>
</tr>
<tr>
	<td>MouseMoveIntervalTime</td>
	<td>Gets/Sets the mouse interval time between mouse moves. The default is set at 15msec. Typically you don't need to change this. If you want to configure the speed of the mouse move, use the Settings.SimulatedMouseMoveSpeed.</td>
</tr>
</table>

It also has the following properties:

<table class="docs">
<tr>
	<th>Method</th><th>Brief Description</th>
</tr>
<tr>
	<td>CalculateOffset</td>
	<td>Calculates the offset from the rectangles given a reference.</td>
</tr>
<tr>
	<td>Click</td>
	<td>Simulate a mouse click event.</td>
</tr>
<tr>
	<td>DetectHotSpot</td>
	<td>Given a rectangle and optionally a cursor, this function will detect the cursor change.</td>
</tr>
<tr>
	<td>DragDrop</td>
	<td>Simulates a mouse drag and drop operation.</td>
</tr>
<tr>
	<td>GetCursorHandle</td>
	<td>Gets the current Win32 cursor handle.</td>
</tr>
<tr>
	<td>HoverOver</td>
	<td>Simulates a mouse hover over operation.</td>
</tr>
<tr>
	<td>MatchCursor</td>
	<td>Tests whether or not the current mouse handle matches a specified handle. Can be used to check if the current mouse cursor is a particular value.</td>
</tr>
<tr>
	<td>Move</td>
	<td>Move the mouse from the start to the end location.</td>
</tr>
<tr>
	<td>TurnWheel</td>
	<td>Simulates moving the mouse wheel by a specified delta.</td>
</tr>
<tr>
	<td>ValidateNonNegativePoint</td>
	<td>Validate that the specified point coordinates is non-negative. If it is negative, it will be reset to zero.</td>
</tr>
</table>