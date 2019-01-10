---
title: Go Through All Grid Cells
page_title: Go Through All Grid Cells
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/silverlight/radgridview/go-through-cells.aspx, /user-guide/code-samples/silverlight/radgridview/go-through-cells
position: 1
---
## Welcome to Test Studio##

*I'd like to go through each cell in a Silverlight RadGridView in order to perform some action or verification.*

##Solution##

This is possible with a coded solution. Here's an example:

Because of the dynamic nature of the Grid control, it's not practical to record a "static" test (i.e. with pre-recorded regular steps) because any changes in the Grid content can cause the test to fail. The sample project attached to the end of this article contains two tests:

* **GoThroughAllCellsInGrid**

* **GoThroughAllVisibleCells**

The first test uses code to go through all the visible cells in the grid (as opposed to all the cells contained within the grid) in a <a href="http://demos.telerik.com/silverlight/#DataVirtualization/FirstLook" target="_blank">Silverlight Demo</a>. It writes the text content of each cell into the test log. You can modify the logic in order to implement another type of verification against the text content. Below is the coded step that does this. Keep in mind that when working with Silverlight in coded steps in Test Studio, you'll need to set the test to Enable Silverlight = true in order to run it from Quick Execution:

![SL enabled][1]

The code can be resued in a Telerik Testing Framework test, but you'll need to add the following line of code:

```
Settings.Current.Web.EnableSilverlight = true;
```

```C#
SilverlightApp app = ActiveBrowser.SilverlightApps()[0]; //Get Silverlight app              
  
Telerik.WebAii.Controls.Xaml.RadGridView rgv = app.Find.ByType<Telerik.WebAii.Controls.Xaml.RadGridView>(); //Get RadGrid
int rowCounter = 1;
  
foreach (Telerik.WebAii.Controls.Xaml.GridViewRow gRow in rgv.Rows) { //Loop to go through all the rows
      
  Log.WriteLine("<-------------Start of row "+rowCounter.ToString()+"------------->"); //Write row number to log
      
  int cellCounter = 1;  
    foreach(Telerik.WebAii.Controls.Xaml.GridViewCell gCell in gRow.Cells) { //Nested loop; Goes through all the cells within each row
          
     Log.WriteLine("Cell "+ cellCounter.ToString()+": "+gCell.Text);   //We output the cell text to the log; 
        //You can implement any type of verification you like against the text here
          
        cellCounter++;
    }
    rowCounter++;
}
```
```VB
Dim app As SilverlightApp = ActiveBrowser.SilverlightApps()(0)
'Get Silverlight app              
Dim rgv As Telerik.WebAii.Controls.Xaml.RadGridView = app.Find.ByType(Of Telerik.WebAii.Controls.Xaml.RadGridView)()

Dim rowCounter As Integer = 1
  
For Each gRow As Telerik.WebAii.Controls.Xaml.GridViewRow In rgv.Rows
    
    Log.WriteLine("<-------------Start of row " + rowCounter.ToString() + "------------->")

    Dim cellCounter As Integer = 1
    For Each gCell As Telerik.WebAii.Controls.Xaml.GridViewCell In gRow.Cells
         Log.WriteLine("Cell " + cellCounter.ToString() + ": " + gCell.Text)
         cellCounter += 1
    Next
    rowCounter += 1
Next
```

The second test, **GoThroughAllCellsInGrid**, scrolls through the Grid and goes through all its cells, not just the ones that are currently visible. Basically it combines the above code with the code from <a href="/advanced-topics/coded-samples/silverlight/radgridview-automation/scrolling" target="_blank">this article</a>.

* Download the <a href="http://docs.telerik.com/teststudio/demoslibrary/RADGridViewAutomation_C.zip">C# project</a>.

[1]: /img/advanced-topics/coded-samples/silverlight/radgridview-automation/go-through-all-grid-cells/fig1.png

