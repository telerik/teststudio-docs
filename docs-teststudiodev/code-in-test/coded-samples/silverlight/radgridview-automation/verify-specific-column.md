---
title: Verify Specific Column
page_title: Verify Specific Column - Test Studio Dev Documentation
description: Verify Specific Column
position: 1
---
# RadGridView Verify Data in a Specific Column #

*I need to find the correct column of a GridView based on something other than index, such as text content or a data driven variable.*

## Solution ##

Here is how to accomplish this against a <a href="http://demos.telerik.com/silverlight/#GridView/Totals" target="_blank">Telerik demo site</a>. First you need to retrieve all the Header Row Cells from the Grid and iterate through each one looking for a specific string. Each time it isn't found, the integer idx is increased by one. Once a match is made, idx will equal the index of the target column. Then you can use that integer to identify the column later:

#### __[C#]__

    {{region }}

    int verticalOffset = 0; // Holds the current vertical offset in the viewport
    int viewPortHeight; // The height of the visible part of the grid
    int extentHeight; // The total height of the grid, visible plus non-visible
    
    // Copy the RadGridView into a local variable as a shortcut
    RadGridView grid = Pages.TelerikGridViewFor1.SilverlightApp.RadGridView1Radgridview;
    
    // Grab the VirtualizingPanel contained in the RadGridView. This is used to control the viewable portion of the grid.
    FrameworkElement VirtualizingPanel = grid.Find.ByType("GridViewVirtualizingPanel");
    
    // Detect the view port height and the extent height
    viewPortHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ViewportHeight", typeof(int)));
    extentHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ExtentHeight", typeof(int)));
    
    VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0);
    
    //get the Header Row Cells and iterate through them
    IList<GridViewHeaderCell> headers = grid.HeaderRow.HeaderCells;
    int idx = 0; 
    foreach(GridViewHeaderCell header in headers)
    {
        //Instead of a sting (here it's "Unit Price"), you can use a variable
        if(header.Text.Equals("Unit Price", StringComparison.CurrentCultureIgnoreCase))  
        {
            break;
        }
        idx++; 
    }
    Assert.IsTrue(idx < headers.Count, string.Format("Column {0} not found", "Unit Price"));
        
    // Walk through the entire grid verifying the data
    while (verticalOffset < extentHeight)
    {
        foreach (GridViewRow r in grid.Rows)
        {
                //Here the integer "idx" is used in place of the actual index number 
                Assert.AreEqual<string>(Data["State"].ToString(), r.Cells[idx].Text.Substring(0,1));
        }
    
        // Scroll down one page
        verticalOffset += viewPortHeight;
        VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset);
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim verticalOffset As Integer = 0

    Dim viewPortHeight As Integer

    Dim extentHeight As Integer
    

    Dim grid As RadGridView = Pages.TelerikGridViewFor1.SilverlightApp.RadGridView1Radgridview
    

    Dim VirtualizingPanel As FrameworkElement = grid.Find.ByType("GridViewVirtualizingPanel")
    

    viewPortHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ViewportHeight", GetType(Integer))))
    extentHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ExtentHeight", GetType(Integer))))
    
    VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0)
    

    Dim headers As IList(Of GridViewHeaderCell) = grid.HeaderRow.HeaderCells
    Dim idx As Integer = 0
    For Each header As GridViewHeaderCell In headers
        'Instead of a sting (here it's "Unit Price"), you can use a variable
        If header.Text.Equals("Unit Price", StringComparison.CurrentCultureIgnoreCase) Then
            Exit For
        End If
        idx += 1
    Next
    Assert.IsTrue(idx < headers.Count, String.Format("Column {0} not found", "Unit Price"))
    

    While verticalOffset < extentHeight
        For Each r As GridViewRow In grid.Rows
            'Here the integer "idx" is used in place of the actual index number 
            Assert.AreEqual(Of String)(Data("State").ToString(), r.Cells(idx).Text.Substring(0, 1))
        Next
    
        
        verticalOffset += viewPortHeight
        VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset)
    End While
    {{endregion}}



