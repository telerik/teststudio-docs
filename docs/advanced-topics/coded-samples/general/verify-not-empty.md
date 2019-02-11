---
title: Verify Not Empty
page_title: Verify Not Empty
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Verify Not Empty#

*I would like to verify the text content of an element is not empty. In other words, that it contains one or more characters.*

This is possible with a coded solution. The example below is against <a href="http://www.w3schools.com/html/html_tables.asp" target="_blank">this W3Schools site</a>.

```C#
HtmlTable table = Find.ByTagIndex<HtmlTable>("table", 0);
HtmlTableRow row = table.Rows[0];
HtmlTableCell cell = row.Cells[1];
 
Log.WriteLine(cell.TextContent);
Assert.IsTrue(cell.TextContent.Length > 0);
```
```VB
Dim table As HtmlTable = Find.ByTagIndex(Of HtmlTable)("table", 0)
Dim row As HtmlTableRow = table.Rows(0)
Dim cell As HtmlTableCell = row.Cells(1)
 
Log.WriteLine(cell.TextContent)
Assert.IsTrue(cell.TextContent.Length > 0)
```