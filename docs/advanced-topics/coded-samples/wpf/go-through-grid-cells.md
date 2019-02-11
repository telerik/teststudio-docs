---
title: Go Through Grid Cells
page_title: Go Through Grid Cells
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/wpf/go-through-cells.aspx, /user-guide/code-samples/wpf/go-through-cells
position: 4
---
#Go Through Each Cell in a WPF RadGridView#

*I would like to go through each cell in a WPF RadGridView and perform some action or verification.*

##Solution##

This is possible with a coded solution. Here's an example that goes through all the visible cells in a WPF demo grid (as opposed to all the cells contained in the grid). It writes the text content of each cell into the test log.

```C#
WpfApplication app = Manager.ActiveApplication;
Assert.IsNotNull(app);
 
Telerik.WebAii.Controls.Xaml.Wpf.RadGridView grid = app.MainWindow.Find.ByName<Telerik.WebAii.Controls.Xaml.Wpf.RadGridView>("RadGridView1");
Assert.IsNotNull(grid);
 
int rowCounter = 1;
 
foreach (Telerik.WebAii.Controls.Xaml.Wpf.GridViewRow gRow in grid.Rows)
{
    Log.WriteLine("<----------Start of Row " + rowCounter.ToString() + "---------->");
     
    int cellCounter = 1;
    foreach (Telerik.WebAii.Controls.Xaml.Wpf.GridViewCell gCell in gRow.Cells)
    {
        Log.WriteLine(gCell.TextBlockContent);
        cellCounter++;
    }
    rowCounter++;
}
```
```VB
Dim app As WpfApplication = Manager.ActiveApplication
Assert.IsNotNull(app)
 
Dim grid As Telerik.WebAii.Controls.Xaml.Wpf.RadGridView = app.MainWindow.Find.ByName(Of Telerik.WebAii.Controls.Xaml.Wpf.RadGridView)("RadGridView1")
Assert.IsNotNull(grid)
 
Dim rowCounter As Integer = 1
 
For Each gRow As Telerik.WebAii.Controls.Xaml.Wpf.GridViewRow In grid.Rows
    Log.WriteLine("<----------Start of Row " + rowCounter.ToString() + "---------->")
 
    Dim cellCounter As Integer = 1
    For Each gCell As Telerik.WebAii.Controls.Xaml.Wpf.GridViewCell In gRow.Cells
        Log.WriteLine(gCell.TextBlockContent)
        cellCounter += 1
    Next
    rowCounter += 1
Next
```



