---
title: Data Driven Find Expressions
page_title: Data Driven Find Expressions | Test Studio Dev Documentation
description: Data Driven Find Expressions
position: 1
---
# Data Driven Find Expressions

*I would like to data drive a find expression and use it to perform an action against or verify an element.*

## Solution

The example below is against this <a href="http://demos.telerik.com/aspnet-mvc/combobox/index" target="_blank">Telerik demo site</a>.

1.Record a *Navigate* to step.
2.Open the drop-down for the ComboBox.
3.Locate the parent element in the DOM Explorer (see below). Here the Unordered List holds all the child List Item elements. Right click it and select **Add to Project Elements**.

![Add to Project][1]

4.Insert a <a href="/code-in-test/features-in-code#Coded-Step" target="_blank">Coded Step</a>.
5.Use the <a href="/features/data-driven-testing/local-data-driven-test" target="_blank">local data</a> to enter values for the find expression.
6.We will use the Find.ByContent method in the coded step. More information can be found in our <a href="/code-in-test/element-identification/finding-page-elements" target="_blank">Finding Page Elements</a> article. Here's the code for our Script Step:

#### __[C#]__

	{{region }}

	HtmlListItem listItem = Pages.TelerikExtensionsForASP.UnorderedList.Find.ByContent<HtmlListItem>(Data["Col1"].ToString());
	Assert.IsNotNull(listItem);
	listItem.Click();
	{{endregion}}

#### __[VB]__

	{{region }}

	Dim listItem As HtmlListItem = Pages.TelerikExtensionsForASP.UnorderedList.Find.ByContent(Of HtmlListItem)(Data("Col1").ToString())
	Assert.IsNotNull(listItem)
	listItem.Click()
	{{endregion}}

7.Test Studio Dev uses the data table to find the element in the list, performs an Assert on it, and then clicks it.

![Execute test][3]

[1]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig1.png
[2]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig2.png
[3]: /img/advanced-topics/coded-samples/general/data-driven-find-expressions/fig3.png
