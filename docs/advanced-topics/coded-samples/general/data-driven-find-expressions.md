---
title: Data Driven Find Expressions
page_title: Data Driven Find Expressions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/general/data-driven-find-expressions.aspx, /user-guide/code-samples/general/data-driven-find-expressions
position: 1
---
#Data Driven Find Expressions#

*I would like to data drive a find expression and use it to perform an action against or verify an element.*

> After 2012 R2, you can create <a href="/features/elements-explorer/find-element#data-driven" target="_blank">data driven find expressions without code</a>.

##Soluiton##

The example below is against this <a href="http://demos.telerik.com/aspnet-mvc/combobox/index" target="_blank">Telerik demo site</a>.

1. Record a *Navigate* to step.
2. Open the drop-down for the ComboBox.
3. Locate the parent element in the DOM Explorer (see below). Here the Unordered List holds all the child List Item elements. Right click it and select **Add to Project Elements**.

	![Add to Project][1]

4. Insert a <a href="/features/custom-steps/script-step" target="_blank">Script Step</a>.
5. Here's what the Local <a href="/features/data-driven-testing/local-data-driven-test" target="_blank">Data table</a> looks like:

	![Data table][2]

6. We will use the Find.ByContent method in the coded step. More information can be found in our <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">Finding Page Elements</a> article. Here's the code for our Script Step:

	```C#
	HtmlListItem listItem = Pages.TelerikExtensionsForASP.UnorderedList.Find.ByContent<HtmlListItem>(Data["Col1"].ToString());
	Assert.IsNotNull(listItem);
	listItem.Click();
	```
	
	```VB
	Dim listItem As HtmlListItem = Pages.TelerikExtensionsForASP.UnorderedList.Find.ByContent(Of HtmlListItem)(Data("Col1").ToString())
	Assert.IsNotNull(listItem)
	listItem.Click()
	```
7. Test Studio uses the data table to find the element in the list, performs an Assert on it, and then clicks it.

	![Execute test][3]

[1]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig1.png
[2]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig2.png
[3]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig3.png


