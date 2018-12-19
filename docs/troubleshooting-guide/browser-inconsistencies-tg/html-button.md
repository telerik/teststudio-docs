---
title: HTML Button
page_title: HTML Button
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# HTML Button

You may receive different results when trying to get an HTML Button value between browsers. To get the value of an element, the Telerik Testing Framework injects JavaScript into the browser and the browser returns a value. Firefox and Chrome read the value of an attribute named "value", while IE returns the inner HTML of the button.

For example, if we have a button defined as follows:

	<button value="Value"> HTML </button>

Internet Explorer will consider the value of the button to be "HTML", while Firefox and Chrome will consider it to be "Value".



