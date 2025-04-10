---
title: Scrolling
page_title: Scrolling
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/silverlight/radgridview/scrolling.aspx, /user-guide/code-samples/silverlight/radgridview/scrolling
position: 1
---
# RadGridView Scrolling

> This issue can now be resolved <a href="/knowledge-base/silverlight-kb/codeless-scrolling-in-virtualized-panel" target="_blank">without code</a>.

*I need to scroll down through the entire GridView verifying the data, because currently only the rows presented in the Visual Tree can be tested.*

## Solution

This is a limitation of the Visual Tree contained in the Silverlight engine. Silverlight puts into the Visual Tree only the UI components necessary to render the page on the screen.
 
Here is an example. Let's say you have a grid that holds 100 rows of data but can only display 20 at a time. Silverlight typically will only put 22 rows of UI elements in the Visual Tree (20 visible plus one above and one below). The only way to get all 100 rows is to scroll down through the entire grid. 
 
The following code demonstrates how to accomplished this on a <a href="http://demos.telerik.com/silverlight/#GridView/UIVirtualization" target="_blank">Telerik demo page</a>.

````C#
int verticalOffset = 0; // Holds the current vertical offset in the viewport
int viewPortHeight; // The height of the visible part of the grid
int extentHeight; // The total height of the grid, visible plus non-visible

// Copy the RadGridView into a local variable as a shortcut
RadGridView grid = Pages.TelerikGridViewFor.SilverlightApp.RadGridView1Radgridview;
// Grab the VirtualizingPanel contained in the RadGridView. This is used to control the viewable portion of the grid.
FrameworkElement VirtualizingPanel = grid.Find.ByType("GridViewVirtualizingPanel");

// Detect the view port height and the extent height
viewPortHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ViewportHeight", typeof(int)));
extentHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ExtentHeight", typeof(int)));

Dictionary<string, int> rowsHash = new Dictionary<string, int>();
// Make sure it is scrolled to the very top
// Walk through the entire grid verifying the data
VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0);
int rowNum = 0;
while (verticalOffset < extentHeight)
{
grid.Refresh();
	foreach (GridViewRow r in grid.Rows)
	{
	string rowId = r.Cells[2].Text;
		if (!rowsHash.Keys.Contains(rowId))
			{
				rowsHash.Add(rowId, rowNum++);
				Console.WriteLine(r.Cells[0].Text + ", " + r.Cells[1].Text + ", " + r.Cells[2].Text + ", " + r.Cells[3].Text + ", " + r.Cells[4].Text + ", " + r.Cells[5].Text + ", " + r.Cells[6].Text);
			}
    }
// Scroll down one page
verticalOffset += viewPortHeight;
VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset);
}
````
````VB

Dim verticalOffset As Integer = 0
' Holds the current vertical offset in the viewport
Dim viewPortHeight As Integer
' The height of the visible part of the grid
Dim extentHeight As Integer
' The total height of the grid, visible plus non-visible
' Copy the RadGridView into a local variable as a shortcut
Dim grid As RadGridView = Pages.TelerikGridViewFor.SilverlightApp.RadGridView1Radgridview
' Grab the VirtualizingPanel contained in the RadGridView. This is used to control the viewable portion of the grid.
Dim VirtualizingPanel As FrameworkElement = grid.Find.ByType("GridViewVirtualizingPanel")

' Detect the view port height and the extent height
viewPortHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ViewportHeight", GetType(Integer))))
extentHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ExtentHeight", GetType(Integer))))

Dim rowsHash As New Dictionary(Of String, Integer)()
' Make sure it is scrolled to the very top
' Walk through the entire grid verifying the data
VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0)
Dim rowNum As Integer = 0
While verticalOffset < extentHeight
grid.Refresh()
For Each r As GridViewRow In grid.Rows
Dim rowId As String = r.Cells(2).Text
If Not rowsHash.Keys.Contains(rowId) Then
rowsHash.Add(rowId, System.Math.Max(System.Threading.Interlocked.Increment(rowNum),rowNum - 1))
Console.WriteLine(r.Cells(0).Text + ", " + r.Cells(1).Text + ", " + r.Cells(2).Text + ", " + r.Cells(3).Text + ", " + r.Cells(4).Text + ", " + r.Cells(5).Text + ", " + r.Cells(6).Text)
End If
Next
' Scroll down one page
verticalOffset += viewPortHeight
VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset)
End While
````

Due to the volume of data contained in the sample RadGridView, this test will take hours to run through it all. But it shows all the necessary steps.  
