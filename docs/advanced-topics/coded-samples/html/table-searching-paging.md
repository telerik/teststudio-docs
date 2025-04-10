---
title: Table Searching & Paging
page_title: Table Searching & Paging
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/table-search-and-paging.aspx, /user-guide/code-samples/html/table-search-and-paging
position: 1
---
# HTML Table Searching and Paging

*I would like to search an HTML table for specific content and continue through the pages until it is found.*

## Solution

This is possible with a coded solution. The example below is against this <a href="http://demos.telerik.com/aspnet-mvc/grid/index" target="_blank">Telerik demo site</a>.

````C#
HtmlTable table = Find.ByExpression<HtmlTable>("id=Grid", "|", "tagIndex=table:1");
HtmlSpan next = Find.ByExpression<HtmlSpan>("class=k-icon k-i-arrow-e");
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("title=Go to the next page");
 
string search = "10275";
bool found = false;
bool disabled = false;
            
while (false == found && false == disabled)
{
    foreach (HtmlTableRow row in table.AllRows)
    {
        foreach (HtmlTableCell cell in row.Cells)
        {
            if (cell.TextContent == search)
            {
                Log.WriteLine("Match found: " + cell.TextContent);
                cell.MouseClick(MouseClickType.LeftDoubleClick);
                System.Threading.Thread.Sleep(1000);
                found = true;
                break;
            }
        }    
        if (true == found)
        {
            break;
        }
    }
    a.Refresh();
    disabled = a.BaseElement.Content.Contains("disabled");
    if (true == found || true == disabled)
    {
        break;
    }
    next.Click();
    System.Threading.Thread.Sleep(1000);
    table.Refresh();
}
````
````VB
Dim table As HtmlTable = Find.ByExpression(Of HtmlTable)("id=Grid", "|", "tagIndex=table:1")
Dim [next] As HtmlSpan = Find.ByExpression(Of HtmlSpan)("class=k-icon k-i-arrow-e")
Dim a As HtmlAnchor =
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("title=Go to the next page")
 
Dim search As String = "10275"
Dim found As Boolean = False
Dim disabled As Boolean = False
 
While False = found AndAlso False = disabled
    For Each row As HtmlTableRow In table.AllRows
        For Each cell As HtmlTableCell In row.Cells
            If cell.TextContent = search Then
                Log.WriteLine("Match found: " + cell.TextContent)
                cell.MouseClick(MouseClickType.LeftDoubleClick)
                System.Threading.Thread.Sleep(1000)
                found = True
                Exit For
            End If
        Next
        If True = found Then
            Exit For
        End If
    Next
    a.Refresh()
    disabled = a.BaseElement.Content.Contains("disabled")
    If True = found OrElse True = disabled Then
        Exit While
    End If
    [next].Click()
    System.Threading.Thread.Sleep(1000)
    table.Refresh()
End While
````