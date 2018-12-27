---
title: Change Find Strategy
page_title:  Change Find Strategy | Test Studio Dev Documentation
description: Change Find Strategy
position: 1
---
# Change Silverlight Find Strategy #

The default behavior of Test Studio Dev is to time out after a certain interval if the element is not found.

*I would like to avoid the Timeout Exception and perform a different set of steps depending on whether the element is found.*

## Solution ##

This is possible with a coded solution. Change the SilverlightApp or any FrameworkElement VisualFind.Strategy value to WhenNotVisibleReturnNull.

The example below is against this <a href="http://www.silverlight.net/content/samples/sl4/toolkitcontrolsamples/run/default.html" target="_blank">Silverlight demo site</a>. After navigating there, click DataGrid in the left-hand menu. Then add a coded step:

#### __[C#]__

    {{region }}

    SilverlightApp app = ActiveBrowser.SilverlightApps()[0];
    FindStrategy originalStrategy = app.Find.Strategy;
    
    try
    {
        app.Find.Strategy = FindStrategy.WhenNotVisibleReturnNull;
        string gridName = "dataGrid";
        DataGrid grid = app.Find.ByName<DataGrid>(gridName);
        
        if (grid != null)
        {
            grid.Wait.ForVisible();
            //Perform actions on the DataGrid
        }
        else   
        {
            //You can throw an exception, or perform alternative steps
            throw new ArgumentException(string.Format("Unable to find the DataGrid named '{0}'!", gridName));
        }
    }
    finally
    {
        app.Find.Strategy = originalStrategy;
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim app As SilverlightApp = ActiveBrowser.SilverlightApps()(0)
    Dim originalStrategy As FindStrategy = app.Find.Strategy
    
    Try
        app.Find.Strategy = FindStrategy.WhenNotVisibleReturnNull
        Dim gridName As String = "dataGrid"
        Dim grid As DataGrid = app.Find.ByName(Of DataGrid)(gridName)
    
        If grid IsNot Nothing Then
        
            grid.Wait.ForVisible()
        Else
        
            Throw New ArgumentException(String.Format("Unable to find the DataGrid named '{0}'!", gridName))
        End If
    Finally
        app.Find.Strategy = originalStrategy
    End Try
    {{endregion}}

**Note:** As is, the IF portion is executed. You can disable step two (treeview item 'DataGrid' select action) to see the ELSE portion execute.
