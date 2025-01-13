---
title: Keyboard Manager
page_title: Keyboard Manager
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---

# The KeyBoard Manager Class

The KeyBoard manager class is used to simulate typing keys on the keyboard. It has the following methods:

<table class="docs">
<tr>
	<th>Method</th><th>Brief Description</th>
</tr>
<tr>
	<td>KeyDown</td>
	<td>Simulates a key down. (Press and hold).</td>
</tr>
<tr>
	<td>KeyPress</td>
	<td>Simulates a keyboard key press. (Key down followed by key up).</td>
</tr>
<tr>
	<td>KeyUp</td>
	<td>Simulates a key up. (Key-Release).</td>
</tr>
<tr>
	<td>TypeText</td>
	<td>Types text one character at a time with a specific typing speed. This function does not support special keywords (e.g. {TAB}, {SPACE}) or special characters like ^, +, etc. To simulate special keys use SendString if you want to send special characters like Ctrl/Shift, etc.</td>
</tr>
</table>

