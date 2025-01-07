---
title: Desktop Manager
page_title: Desktop Manager
description: "Test Studio Testing Framework support in coded tests for interactions between the execution machine and browser through the DesktopManager class. "
position: 1
---

#The Desktop Manager Class

The Desktop manager class is used to control interaction between the Windows desktop and the browser. It also contains instances of the Keyboard and Mouse managers. It has the following properties:

<table class="docs">
<tr>
	<th>Property</th><th>Brief Description</th>
</tr>
<tr>
	<td>KeyBoard</td>
	<td>Gets the keyboard object that enables simulating real keyboard events.</td>
</tr>
<tr>
	<td>Mouse</td>
	<td>Gets the mouse object that enables simulating real mouse events.</td>
</tr>
<tr>
	<td>ValidateMouseActionsWithinBrowserContent</td>
	<td>Gets/Sets whether to validate all mouse actions to ensure they are within the browser's content window. If this is set to true, any mouse action outside that region will throw an exception.</td>
</tr>
</table>

It also has the following methods:

<table class="docs">
<tr>
	<th style="width: 268px;">Method</th><th>Brief Description</th>
</tr>
<tr>
	<td>DisableAutoDomRefresh</td>
	<td>The most recent launched browser instance. You can use it to invoke actions, access the loaded document DOM and perform element identification an extraction using the Browser.Find object.</td>
</tr>
<tr>
	<td>EnableAutoDomRefresh</td>
	<td>Enables the Desktop Mouse/Keyboard objects to perform auto DOM refreshes after Click/DragDrop/SendKey actions.</td>
</tr>
</table>