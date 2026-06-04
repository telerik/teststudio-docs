---
title: Drag & Drop
page_title: Drag & Drop
description: "Test Studio Testing Framework Drag&Drop  actions in coded tests. Use the DragTo() methods to define the desired action to drag an element and drop it on specific point."
position: 2
---
# How to Drag and Drop

The HTML element wrapper classes make mouse drag & drop operations significantly easier. There are 7 different drag methods defined:

````C#
public virtual void DragTo(ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl control)

public virtual void DragTo(System.Drawing.Point absolutePoint)

public virtual void DragTo(int offsetX, int offsetY)

public virtual void DragTo(ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl control, 
ArtOfTest.Common.OffsetReference destinationOffsetReference, System.Drawing.Point destinationOffset)

public virtual void DragTo(ArtOfTest.Common.OffsetReference sourceOffsetReference, System.Drawing.Point sourceOffset, ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl destination)

public virtual void DragTo(ArtOfTest.Common.OffsetReference sourceOffsetReference, System.Drawing.Point sourceOffset, int destinationOffsetX, int destinationOffsetY)

public virtual void DragTo(ArtOfTest.Common.OffsetReference sourceOffsetReference, int sourceOffsetX, int sourceOffsetY, bool sourcePixelDrag, ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl destination, ArtOfTest.Common.OffsetReference destinationOffsetReference, int destinationOffsetX, int destinationOffsetY, bool destinationPixelDrop)
````

Suppose we have a sales by area table that supports drag & drop between cells. We can easily drag & drop the contents of one cell to another cell like this:

````C#
// Find the sales table
HtmlTable salesTable = Find.ById<HtmlTable>("area_1_table");
  
// Drag the data from row 4 to row 3 using the method which takes the controls only
salesTable.BodyRows[3].Cells[1].DragTo(salesTable.BodyRows[2].Cells[1]);

// Drag the data from row 4 to row 3 using the method which takes the complete set of preferences (the last listed). It allows you to specify the dragged and dropped elements, the offset to use for both, coordinates as per this offset, and whether to use pixels or percentage.
salesTable.BodyRows[3].Cells[1].DragTo(ArtOfTest.Common.OffsetReference.AbsoluteCenter, 0, 0, true, salesTable.BodyRows[2].Cells[1], ArtOfTest.Common.OffsetReference.AbsoluteCenter, 0, 0, true)
  
// Verify the new row subtotals are correct
Assert.AreEqual(salesTable.Rows[2].Cells[5].TextContent, "$3342.78");
Assert.AreEqual(salesTable.Rows[3].Cells[5].TextContent, "$2175.17");
````
````VB
' Find the sales table
Dim salesTable As HtmlTable = Find.ById(Of HtmlTable)("area_1_table")
  
' Drag the data from row 4 to row 3
salesTable.BodyRows(3).Cells(1).DragTo(salesTable.BodyRows(2).Cells(1))
  
' Verify the new row subtotals are correct
Assert.AreEqual(salesTable.Rows(2).Cells(5).TextContent, "$3342.78")
Assert.AreEqual(salesTable.Rows(3).Cells(5).TextContent, "$2175.17")
````
