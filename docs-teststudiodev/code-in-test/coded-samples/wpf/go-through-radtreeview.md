---
title: Go Through RadTreeView
page_title: Go Through RadTreeView | Test Studio Dev Documentation
description: Go Through RadTreeView
position: 3
---
# Go Through Each Node in a WPF RadTreeView #

*I would like to go through each node in a WPF RadTreeView until a match is made.*

## Solution ##

This is possible with a coded solution. You'll expand each node and refresh the tree until you find your match.

#### __[C#]__

    {{region }}

    WpfApplication app = Manager.ActiveApplication;
    Assert.IsNotNull(app);
    Telerik.WebAii.Controls.Xaml.Wpf.RadTreeView tree = app.MainWindow.Find.ByName<Telerik.WebAii.Controls.Xaml.Wpf.RadTreeView>("treeView");
    Assert.IsNotNull(tree);
    
    string match = Data["ExtractedValue"].ToString();
    bool found = false;
    IList<Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem> items = tree.Find.AllByType<Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem>();
    
    while (found == false)
    {
        foreach (Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem tvItem in items)
        {
            try
            {
                if (tvItem.IsExpanded == false)
                {
                    tvItem.Expand();
                    tree.Refresh();
                }
            }
            catch (Exception ex)
            {
            }
    
            if (tvItem.Text.Contains(match))
            {
                Log.WriteLine("Found: " + tvItem.Text);
                found = true;
                break;
            }
    
            tree.Refresh();
        }
        if (found == true)
        {
            break;
        }
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim app As WpfApplication = Manager.ActiveApplication
    Assert.IsNotNull(app)
    Dim tree As Telerik.WebAii.Controls.Xaml.Wpf.RadTreeView = app.MainWindow.Find.ByName(Of Telerik.WebAii.Controls.Xaml.Wpf.RadTreeView)("treeView")
    Assert.IsNotNull(tree)
    
    Dim match As String = Data("ExtractedValue").ToString()
    Dim found As Boolean = False
    Dim items As IList(Of Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem) = tree.Find.AllByType(Of Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem)()
    
    While found = False
        For Each tvItem As Telerik.WebAii.Controls.Xaml.Wpf.RadTreeViewItem In items
            Try
                If tvItem.IsExpanded = False Then
                    tvItem.Expand()
                    tree.Refresh()
                End If
            Catch ex As Exception
            End Try
    
            If tvItem.Text.Contains(match) Then
                Log.WriteLine("Found: " + tvItem.Text)
                found = True
                Exit For
            End If
    
            tree.Refresh()
        Next
        If found = True Then
            Exit While
        End If
    End While
    {{endregion}}


