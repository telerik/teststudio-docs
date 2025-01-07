---
title: Verify Not Empty
page_title: Verify The Text Content of an Element is Not Empty
description: "Verify the text content of an element is not empty in Test Studio test run."
position: 1
---
# Verify Not Empty 

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