---
title: Verify Sort Order
page_title: Verify Sort Order
description: "Learn how to verify the sort order of an HTML table column in Test Studio using C#. This guide provides a coded solution to ensure data is sorted correctly during automated testing."
previous_url: /user-guide/code-samples/html/verify-sort-order.aspx, /user-guide/code-samples/html/verify-sort-order
position: 1
---
#Verify Sort Order in an HTML Table#

*I would like to sort a column in an HTML Table and verify the content is in the correct order.*

##Solution##

This is possible with a coded solution. The example below is against this <a href="http://demos.telerik.com/aspnet-mvc/grid/index" target="_blank">Telerik demo site</a>.
 
Let's verify the first column, Order ID, is in sequential order:

```C#
//Get the table.
HtmlTable table = Find.ByExpression<HtmlTable>("id=Grid", "|", "tagIndex=table:1");
 
int r = table.Rows.Count;
List<string> list = new List<string>();
  
//Place the text content of the Order ID cell from each row into the string list.
for (int i = 0; i < r; i++)
{
    HtmlTableRow row = table.Rows[i];
    HtmlTableCell cell = row.Cells[0];  
    list.Add(cell.TextContent);
    Log.WriteLine(cell.TextContent);
}
  
//Assert each string in the list is greater than the string before it.
for (int j = 0; j < list.Count; j++)
{
    if (j+1 == list.Count)
    {
        break;
    }
    else
    {
        Assert.IsTrue(list[j+1].CompareTo(list[j]) >= 0);
    }
}
```
```VB
Dim table As HtmlTable = Find.ByExpression(Of HtmlTable)("id=Grid", "|", "tagIndex=table:1")
 
Dim r As Integer = table.Rows.Count
Dim list As New List(Of String)()
 

For i As Integer = 0 To r - 1
    Dim row As HtmlTableRow = table.Rows(i)
    Dim cell As HtmlTableCell = row.Cells(0)
    list.Add(cell.TextContent)
    Log.WriteLine(cell.TextContent)
Next
 

For j As Integer = 0 To list.Count - 1
    If j + 1 = list.Count Then
        Exit For
    Else
        Assert.IsTrue(list(j + 1).CompareTo(list(j)) >= 0)
    End If
Next
```
