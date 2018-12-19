---
title: Parsing Error
page_title: Resolving Errors Related to Invalid HTML Code
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Resolving Errors Related to Invalid HTML Code

## PROBLEM

You get the following error message while attempting to record your application:

*This element cannot be found in the current page. There's probably a problem parsing the page source, make sure the source is valid!*

## SOLUTION

This message indicates that Test Studio has encountered invalid HTML code that can't be correctly parsed. Most web pages contain HTML errors. The majority of these are minor and do not seriously affect the way the page is displayed in a browser or how it is parsed by Test Studio. Some errors, however, can be serious enough to cause Test Studio's parser to crash. If so, you'll see the above warning message. The HTML error may or may not be visible when the HTML code is rendered inside a browser. Keep in mind that browser types interpret HTML differently. Some have a lower tolerance threshold than others when it comes to HTML errors. 

An HTML validator can help you determine if HTML errors exist. There are many validators available <a href="http://validator.w3.org/#validate_by_input" target="_blank">online</a>. Once you've repaired your page, try to record against it again. 

**The End Tag**

Some HTML elements might display correctly even if you forget the end tag:

	<p>This is a paragraph
	<p>This is a paragraph

The example above works in most browsers because the closing tag is considered optional. Never rely on this. Many HTML elements will produce unexpected results or errors if you forget the end tag.

Reference: <a href="http://www.w3schools.com/html/html_elements.asp" target="_blank"> W3Schools</a>