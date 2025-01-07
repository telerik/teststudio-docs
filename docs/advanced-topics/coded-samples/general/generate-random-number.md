---
title: Generate Random Number
page_title: Generate Random Number
description: "Generate Random Number in Test Studio coded test."
previous_url: /user-guide/code-samples/general/random-number-input.aspx, /user-guide/code-samples/general/random-number-input
position: 1
---
# Generate Random Number

*I would like to generate a random number in Test Studio. This number will be used in an input control or for a similar purpose.*

## Solution

This is possible with a coded solution. The .NET Framework provides the <a href="http://msdn.microsoft.com/en-us/library/system.random.aspx" target="_blank">System.Random</a> class which can be used to generate random numbers.

In this example, we'll navigate to <a href="http://demos.telerik.com/aspnet-ajax/listview/examples/paging/pagingwithraddatapager/defaultcs.aspx" target="_blank">this Telerik demo page</a> and use the DataPager control to navigate to a random page number between 1 and 10.

```C#
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/datapager/examples/firstlook/defaultcs.aspx");
             
System.Random random = new  System.Random();
int randomPage = random.Next(1, 11);
             
Find.ByExpression<HtmlInputText>("id=~TextBox_text").Text = randomPage.ToString();
Find.ByExpression<HtmlInputControl>("id=~GoToPageButton").Click();
```
```VB
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/datapager/examples/firstlook/defaultcs.aspx")
 
Dim random As New System.Random()
Dim randomPage As Integer = random.[Next](1, 11)
 
Find.ByExpression(Of HtmlInputText)("id=~TextBox_text").Text = randomPage.ToString()
Find.ByExpression(Of HtmlInputControl)("id=~GoToPageButton").Click()
```