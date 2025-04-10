---
title: Total Rows Count
page_title: Total Rows Count
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/silverlight/radgridview/total-rows-count.aspx, /user-guide/code-samples/silverlight/radgridview/total-rows-count
position: 1
---
# RadGridView Total Rows Count 

*I need to get the total number of rows contained in a RadGridView. The Rows.Count property of the RadGridView only returns the number of rows on the current page.*

## Solution

The only way to get the total rows count is by calculating the number of rows per page and adding them to the running total.

The following code demonstrates how to get the rows count of the RadGridView shown on this <a href="http://demos.telerik.com/silverlight/#GridView/PagingLargeData" target="_blank">Telerik demo site</a>. We use a Do/While loop in code which exits once the "Next Page" button is no longer Enabled. Then the row count is performed once more to account for the last page.

````C#
int extentHeight; // The total height of the grid, visible plus non-visible
int rowHeight; // The height of the row
  
// Copy the RadGridView into a local variable as a shortcut
RadGridView grid = Pages.TelerikGridViewFor2.SilverlightApp.GridViewRadgridview;
  
// Grab the VirtualizingPanel contained in the RadGridView. This is used to control the viewable portion of the grid.
FrameworkElement VirtualizingPanel = grid.Find.ByType("GridViewVirtualizingPanel");
  
// Detect the extent height and the row height
extentHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ExtentHeight", typeof(int)));
rowHeight = (int)grid.GetProperty(new AutomationProperty("RowHeight", typeof(int)));
  
int totalPageRows = 0;    
int totalOverallRows = 0;
// Calculate the total overall rows until the "Next Page" is no longer Enabled 
do
{
totalPageRows = (extentHeight/rowHeight);
totalOverallRows = totalPageRows + totalOverallRows;
      
Pages.TelerikGridViewFor2.SilverlightApp.MoveToNextPageButtonRadbutton.User.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick);
}
while(Pages.TelerikGridViewFor2.SilverlightApp.MoveToNextPageButtonRadbutton.IsEnabled);
  
totalPageRows = (extentHeight/rowHeight);
totalOverallRows = totalPageRows + totalOverallRows;
  
// Show the result
Log.WriteLine("Total Number of Rows: "+ totalOverallRows.ToString());
````
````VB
Dim extentHeight As Integer

Dim rowHeight As Integer


Dim grid As RadGridView = Pages.TelerikGridViewFor2.SilverlightApp.GridViewRadgridview
 

Dim VirtualizingPanel As FrameworkElement = grid.Find.ByType("GridViewVirtualizingPanel")
 

extentHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ExtentHeight", GetType(Integer))))
rowHeight = CInt(grid.GetProperty(New AutomationProperty("RowHeight", GetType(Integer))))
 
Dim totalPageRows As Integer = 0
Dim totalOverallRows As Integer = 0
 
Do
    totalPageRows = (extentHeight / rowHeight)
    totalOverallRows = totalPageRows + totalOverallRows
 
    Pages.TelerikGridViewFor2.SilverlightApp.MoveToNextPageButtonRadbutton.User.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick)
Loop While Pages.TelerikGridViewFor2.SilverlightApp.MoveToNextPageButtonRadbutton.IsEnabled
 
totalPageRows = (extentHeight / rowHeight)
totalOverallRows = totalPageRows + totalOverallRows
 

Log.WriteLine("Total Number of Rows: " + totalOverallRows.ToString())
````
