---
title: Verify Sort Order
page_title: Verify Sort Order
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/silverlight/verify-sort-order.aspx, /user-guide/code-samples/silverlight/verify-sort-order
position: 1
---
#Verify Sort Order in a Silverlight DataGrid#

I would like to sort a column in a Silverlight DataGrid and verify the content is in the correct order.

##Solution##

This is possible with a coded solution. The example below is against <a href="http://silverlight.codeplex.com/downloads/get/119862" target="_blank">a Silverlight toolkit sample</a>.
 
After navigating there, click DataGrid in the left-hand menu. Then click the **FirstName** column header to sort that column. Finally, add a coded step:

```C#
//Get the data grid.
SilverlightApp app = ActiveBrowser.SilverlightApps()[0];
DataGrid grid = app.Find.ByAutomationId<DataGrid>("dataGrid");
 
int r = grid.Rows.Count;
List<string> list = new List<string>();
 
//Place the TextBlock content of the FirstName cell from each row into the string list.
for (int i = 0; i < r; i++)
{
    DataGridRow row = grid.Rows[i];
    DataGridCell cell = row.Cells[2];   
    list.Add(cell.TextBlockContent);
    Log.WriteLine(cell.TextBlockContent);
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

Dim app As SilverlightApp = ActiveBrowser.SilverlightApps()(0)
Dim grid As DataGrid = app.Find.ByAutomationId(Of DataGrid)("dataGrid")
 
Dim r As Integer = grid.Rows.Count
Dim list As New List(Of String)()
 

For i As Integer = 0 To r - 1
    Dim row As DataGridRow = grid.Rows(i)
    Dim cell As DataGridCell = row.Cells(2)
    list.Add(cell.TextBlockContent)
    Log.WriteLine(cell.TextBlockContent)
Next
 

For j As Integer = 0 To list.Count - 1
    If j + 1 = list.Count Then
        Exit For
    Else
        Assert.IsTrue(list(j + 1).CompareTo(list(j)) >= 0)
    End If
Next
```


