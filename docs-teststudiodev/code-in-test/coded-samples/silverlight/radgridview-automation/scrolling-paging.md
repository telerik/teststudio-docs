---
title: Scrolling & Paging
page_title: Scrolling & Paging | Test Studio Dev Documentation
description: Scrolling & Paging
position: 1
---
# RadGridView Scrolling & Paging #

*I have a lot of data contained in a RadGridView with scrolling and paging. I need to find a specific element in the grid. To find it, I need to scroll down through the entire GridView and go through every page verifying the data.*

![Paging][1]

## Solution ##

This is possible with a coded solution. To accomplish the main goal, we need to combine the solutions of the two sub-problems. We need to take the following steps to implement the solution:

1.Change the default <a href="/acode-in-test/coded-samples/silverlight/change-find-strategy" target="_blank">Find Strategy</a> of the Grid to *WhenNotVisibleReturnNull*, otherwise the Find method will return a *FindElementException* if the element is not found.

2.Scroll down to the bottom of the Grid.

3.Go through the Grid page by page, repeating step two until the desired element is found

The following code demonstrates how to accomplish this on a <a href="http://demos.telerik.com/silverlight/#GridView/PagingLargeData" target="_blank">Telerik demo site</a>.

#### __[C#]__

    {{region }}

    public FrameworkElement FindElementByTextContent(string content)
    {
        int extentHeight; // The total height of the grid, visible plus non-visible     
        int rowHeight; // The height of the row
        int viewPortHeight; // The height of the visible part of the grid
        int verticalOffset = 0; // Holds the current vertical offset in the viewport
        
        // Copy the RadGridView into a local variable as a shortcut
        RadGridView grid = Pages.TelerikGridViewFor.SilverlightApp.GridViewRadgridview;
        
        // Grab the VirtualizingPanel contained in the RadGridView. This is used to control the viewable portion of the grid.
        FrameworkElement VirtualizingPanel = grid.Find.ByType("GridViewVirtualizingPanel");
        
        // Detect the extent height, view port height and the row height
        extentHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ExtentHeight", typeof(int)));
        rowHeight = (int)grid.GetProperty(new AutomationProperty("RowHeight", typeof(int)));
        viewPortHeight = (int)VirtualizingPanel.GetProperty(new AutomationProperty("ViewportHeight", typeof(int)));
        
        //Save the original find Find Strategy
        FindStrategy originalStrategy = grid.Find.Strategy;
        
        //Change the Find Strategy for the RadGridView
        grid.Find.Strategy = FindStrategy.WhenNotVisibleReturnNull;
        
        // Scroll through each RadGridView page until the element is found or until the "Next Page" is no longer Enabled  
        do
        {
            verticalOffset = 0;
            VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0);
            while (verticalOffset < extentHeight)
            {          
                    FrameworkElement fe = grid.Find.ByTextContent(content);
                    if(fe != null)
                    {  
                        //Return the original strategy
                        grid.Find.Strategy = originalStrategy;
                        
                        //Return the element
                        return fe;
                    }
                    
                    verticalOffset += viewPortHeight;
                    VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset); 
            
            }
            Pages.TelerikGridViewFor.SilverlightApp.MoveToNextPageButtonRadbutton.User.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick);
        }
        while(Pages.TelerikGridViewFor.SilverlightApp.MoveToNextPageButtonRadbutton.IsEnabled);
        
        //Return the original strategy
        grid.Find.Strategy = originalStrategy;
        return null;
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Public Function FindElementByTextContent(content As String) As FrameworkElement
        
        Dim extentHeight As Integer
        
        Dim rowHeight As Integer
    
        Dim viewPortHeight As Integer
        
        Dim verticalOffset As Integer = 0
    
        
        Dim grid As RadGridView = Pages.TelerikGridViewFor.SilverlightApp.GridViewRadgridview
    
        
        Dim VirtualizingPanel As FrameworkElement = grid.Find.ByType("GridViewVirtualizingPanel")
    
        
        extentHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ExtentHeight", GetType(Integer))))
        rowHeight = CInt(grid.GetProperty(New AutomationProperty("RowHeight", GetType(Integer))))
        viewPortHeight = CInt(VirtualizingPanel.GetProperty(New AutomationProperty("ViewportHeight", GetType(Integer))))
    
        
        Dim originalStrategy As FindStrategy = grid.Find.Strategy
    
        
        grid.Find.Strategy = FindStrategy.WhenNotVisibleReturnNull
    
        
        Do
            verticalOffset = 0
            VirtualizingPanel.InvokeMethod("SetVerticalOffset", 0)
            While verticalOffset < extentHeight
                Dim fe As FrameworkElement = grid.Find.ByTextContent(content)
                If fe IsNot Nothing Then
                    
                    grid.Find.Strategy = originalStrategy
    
                    
                    Return fe
                End If
    
                verticalOffset += viewPortHeight
    
                VirtualizingPanel.InvokeMethod("SetVerticalOffset", verticalOffset)
            End While
            Pages.TelerikGridViewFor.SilverlightApp.MoveToNextPageButtonRadbutton.User.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick)
        Loop While Pages.TelerikGridViewFor.SilverlightApp.MoveToNextPageButtonRadbutton.IsEnabled
    
        
        grid.Find.Strategy = originalStrategy
        Return Nothing
    End Function
    {{endregion}}
    
Place this in the code-behind and then call this method from a coded step.

[1]: images/scrolling-paging/fig1.png
