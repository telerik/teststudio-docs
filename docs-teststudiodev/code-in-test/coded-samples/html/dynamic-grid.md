---
title: Dynamic Grid
page_title: Dynamic Grid - Test Studio Dev Documentation
description: Dynamic Grid
position: 1
---
# Automating a Dynamically Generated Grid

*I need to automate an ASP .NET Grid control like the one seen <a href="http://demos.telerik.com/aspnet-ajax/grid/examples/client/selecting/defaultcs.aspx" target="_blank">here</a>.*

>**Note:** this is a Telerik-manufactured RadControl but this solution applies to generic/custom grids as well.

## Solution

This can be achieved through a coded solution. As you can see the page listed above contains a Grid. Fist we need to add this Grid to our project. In the Test Studio Dev project open a web test, start recording and navigate to the page.

Using the <a href="/features/recorder/highlighting-elements" target="_blank">highlighting</a> feature in the recorder hover the mouse over the grid. Since this is a Telerik-manufactured ASP .Net grid, the <a href="/features/recorder/translators" target="_blank">Translators</a> will kick-in and you will see multiple options depending on which specific part of the grid you've hovered over:

![Highlight][1]

Each of the rectangles represents a specific layer of the Grid. We're interested in the GridTableView, which is the second last rectangle in the image. Don't choose the actual GridView - it corresponds to a div element.

Now bring up the pop up menu and click on "Add to Elements":

![Add to project][2]

 >__Note:__ Adding a generic grid into the Elements repository will be slightly different because highlighting the actual grid element might not be so easy. You might need to bring up the <a href="/features/recorder/dom-explorer" target="_blank">DOM Explorer</a> and locate and add the grid from there).

Going back to Test Studio Dev project, you will notice a new element has appeared in Project Elements and it will be highlighted by a yellow arrow:

![Add to project][3]

## Outputting the content of each (visible) cell to the Log

Create a new coded step and add the following lines that go through each (visible) cell in the Grid:

````C#
    foreach (HtmlTableRow r in Pages.ClientSideRowSelection.ContentPlaceholder1RadGrid1Table.AllRows)
    {
        foreach(HtmlTableCell c in r.Cells)
        {
            Log.WriteLine("Cell found. TextContent:"+c.TextContent);  
        }
    }
````

This is C# code, the VB code will follow the same logic only transcribed in the corresponding syntax. Make sure the coded step executes at a point in your test when the page contains the grid fully loaded in the currently active browser.

## Locate a specific row and click on a specific cell in that row

Let's look at the grid in the below image. Let's imagine we want to get the row that contains the Contact Name "Thomas Hardy" and from there we want to click the checkbox in the same row

![Get a particular row][4]

In this example we want to check a checkbox but this could be any kind of control. The code we will use doesn't take into account what the content of the actual cell is: we just click it. Once again we'll be using the definition of the grid that we've stored in the the elements repository. Here's the code:

````C#
    HtmlTableRow containerRow=null; //The variable that will store the row that contains the name cell and the checkbox cell

    foreach (HtmlTableRow r in Pages.ClientSideRowSelection.ContentPlaceholder1RadGrid1Table.AllRows)
    {
        //Go through all the cells to find the one that contains the name;
        //This assumes you won't know which column has the name.
    foreach(HtmlTableCell c in r.Cells) 
        {
    
            if (c.TextContent.Equals("Thomas Hardy")) //The name can be data-driven if you use code that will extract values from a datasource
            {
            containerRow = c.Parent<HtmlTableRow>(); //We want to get the row which has this cell   
            }
                
    }
    }

    HtmlTableCell checkbox = containerRow.Cells[0]; //Get the cell with the checkbox

    checkbox.ScrollToVisible();

    checkbox.MouseClick();
````

[1]: images/dynamic-grid/fig1.png
[2]: images/dynamic-grid/fig2.png
[3]: images/dynamic-grid/fig3.png
[4]: images/dynamic-grid/fig4.png
[5]: images/dynamic-grid/fig5.png


