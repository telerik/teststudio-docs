---
title: Dynamic Grid
page_title: Dynamic Grid
description: "Automating a dynamic grid - how to overcome the challenge that the content of the cells in grid changes? The recorded elements use the text content of cells which changes and I can't execute the tests unless if I don't change the find expressions of elements.  How can avoid constant update of grid elements?"
position: 1
---
# Automating a Dynamically Generated Grid

You need to automate an ASP .NET Grid control like the one seen <a href="http://demos.telerik.com/aspnet-ajax/grid/examples/client/selecting/defaultcs.aspx" target="_blank">here</a>.

**Note:** this is a Telerik-manufactured RadControl but this solution applies to generic/custom grids as well.

## Solution

This can be achieved in both the Standalone version and Visual Studio plugin through a coded solution. We will use <a href="http://demos.telerik.com/aspnet-ajax/grid/examples/client/selecting/defaultcs.aspx" target="_blank">this grid</a> to demonstrate how to do it.

As you can see this page contains a Grid. Fist we need to add this Grid to our project. From your Test Studio project, start the Recorder and navigate to the page.  

Using Hover Over Highlighting, highlight the Grid. Since this is a Telerik-manifactured ASP .Net grid, the <a href="http://docs.telerik.com/teststudio/getting-started/test-recording/translators" target="_blank">Translators</a> will kick-in and you will see multiple options depending on which specific part of the Grid you've hovered over: 

![Highlight][1]

Each of the rectangles represents a specific layer of the Grid. We're interested in the GridTableView, which is the second last rectangle in the image. Don't choose the actual GridView - it corresponds to a DIV element. 

Now bring up the pop up menu and click on "Add to Elements":

![Add to project][2]

 (Note: adding a generic Grid into Project Elements will be slightly different because highlighting the actual Grid element might not be so easy. You might need to bring up the <a href="/features/recorder/dom-explorer" target="_blank">DOM Explorer</a> and locate and add the Grid from there).

Going back to Test Studio, you will notice a new element has appeared in Project Elements and it will be highlighted by a yellow arrow:

![Add to project][3]

## Outputting the content of each (visible) cell to the Log

Create a new coded step and add the following lines that go through each (visible) cell in the Grid:

```C#
foreach (HtmlTableRow r in Pages.TelerikWebUIGridRow.ContentPlaceholder1RadGrid1Table.AllRows)
{
    foreach(HtmlTableCell c in r.Cells)
    {
        Log.WriteLine("Cell found. TextContent: "+c.TextContent);  
    }
}
```

This is C# code, the VB code will follow the same logic only transcribed in the corresponding syntax. Make sure the coded steps executes at a point in your test when the page congaing the Grid is loaded in the Active Browser.

## Locate a specific row and click on a specific cell in that row

Let's look at the grid in the below image. Let's imagine we want to get the row that contains the Contact Name "Thomas Hardy" and from there we want to click the checkbox in the same Row:

![Get a particular row][4]

In this example we want to click a checkbox but the nested control in the grid may be any other type. To adjust it you will need to change the <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">Find.ByXX statement</a>. For this example we again use the definition of the Grid that we've stored in the Project's Elements Explorer (as seen in Solution 1 of this article). Here's the code:

```C#
//The variable that will store the row which contains the name cell and the checkbox cell
HtmlTableRow containerRow=null; 

foreach (HtmlTableRow r in Pages.TelerikWebUIGridRow.ContentPlaceholder1RadGrid1Table.AllRows)
{
    //Go through all the cells to find the one that contains the name;
    //This assumes you won't know which column has the name.
   foreach(HtmlTableCell c in r.Cells) 
    {
   
        if (c.TextContent.Equals("Thomas Hardy")) //The name can be data-driven if you use code that will extract values from a datasource
        {
            containerRow = c.Parent<HtmlTableRow>(); //We want to get the row which has this cell

            // Use the below lines while working on setting up the coded solution
            // This statement outputs the inner text content of each cell in the 
            // containerRow along with its index and can help with identifying which cell 
            // to use later
            foreach(HtmlTableCell cell in containerRow.Cells)
            {
                Log.WriteLine("Cell index is " + cell.CellIndex.ToString()+" and its content is: " + cell.InnerText);
            }   
        }   
  }
}

// Find the chekcbox element under the respective cell from the containerRow
HtmlInputCheckBox checkbox = containerRow.Cells[0].Find.ByAttributes<HtmlInputCheckBox>("type=checkbox");
Assert.IsNotNull(checkbox);
// Scroll the element to be visible and click on it
checkbox.ScrollToVisible(ScrollToVisibleType.ElementCenterAtWindowCenter);
checkbox.MouseClick();
```

[1]: /img/advanced-topics/coded-samples/html/dynamic-grid/fig1.png
[2]: /img/advanced-topics/coded-samples/html/dynamic-grid/fig2.png
[3]: /img/advanced-topics/coded-samples/html/dynamic-grid/fig3.png
[4]: /img/advanced-topics/coded-samples/html/dynamic-grid/fig4.png
[5]: /img/advanced-topics/coded-samples/html/dynamic-grid/fig5.png
