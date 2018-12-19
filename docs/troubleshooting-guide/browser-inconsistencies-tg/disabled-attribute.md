---
title: Disabled Attribute
page_title: Disabled Attribute
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Disabled Attribute

The disabled attribute can be rendered differently based on browser. Here are three ways to indicate a Submit button is disabled:


	//Method 1
	<input type="submit" value="Submit" disabled />
 
	//Method 2
	<input type="submit" value="Submit" disabled="" />
 
	//Method 3
	<input type="submit" value="Submit" disabled="disabled" />

![Submit][1]

Build an <a href="/features/verifications/advanced-verification" target="_blank">Advanced Verification</a> so the step passes no matter how the browser renders the HTML:

![Verification][2]

Based on "**Content**", verify that the "**OuterMarkup**" "**Contains**" the word "**disabled**".

> To verify an element is enabled (not disabled), change the second drop-down to "**NotContain**".

For more information, please read our KB article on <a href="/knowledge-base/verification-kb/disabled-attribute-html" target="_blank">How to Verify the Disabled Attribute (HTML)</a>.

[1]: /img/troubleshooting-guide/browser-inconsistencies-tg/disabled-attribute/fig1.png
[2]: /img/troubleshooting-guide/browser-inconsistencies-tg/disabled-attribute/fig2.png