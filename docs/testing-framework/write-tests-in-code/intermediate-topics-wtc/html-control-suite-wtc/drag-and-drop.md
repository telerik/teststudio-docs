---
title: Drag & Drop
page_title: Drag & Drop
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#How to Drag and Drop#

The HTML element wrapper classes make mouse drag & drop operations significantly easier. There are 7 different drag methods defined:

* public virtual void DragTo(_ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl_ control)

* public virtual void DragTo(_System.Drawing.Point_ absolutePoint)

* public virtual void DragTo(_int_ offsetX, _int_ offsetY)

* public virtual void DragTo(_ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl_ control, 
_ArtOfTest.WebAii.Core.OffsetReference destinationOffsetReference_, _System.Drawing.Point_ destinationOffset)

* public virtual void DragTo(_ArtOfTest.WebAii.Core.OffsetReference_ sourceOffsetReference, _System.Drawing.Point_ sourceOffset, _ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl_ destination)

* public virtual void DragTo(_ArtOfTest.WebAii.Core.OffsetReference_ sourceOffsetReference, _System.Drawing.Point_ sourceOffset, _int_ destinationOffsetX, _int_ destinationOffsetY)

* public virtual void DragTo(_ArtOfTest.WebAii.Core.OffsetReference_ sourceOffsetReference, _int_ sourceOffsetX, _int_ sourceOffsetY, _bool_ sourcePixelDrag, _ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl_ destination, _ArtOfTest.WebAii.Core.OffsetReference_ destinationOffsetReference, _int_ destinationOffsetX, _int_ destinationOffsetY, _bool_ destinationPixelDrop)

Suppose we have a sales by area table that supports drag & drop between cells. We can easily drag & drop the contents of one cell to another cell like this:

```C#
// Find the sales table
HtmlTable salesTable = Find.ById<HtmlTable>("area_1_table");
  
// Drag the data from row 4 to row 3 using the method which takes the controls only
salesTable.BodyRows[3].Cells[1].DragTo(salesTable.BodyRows[2].Cells[1]);

// Drag the data from row 4 to row 3 using the method which takes the complete set of preferences (the last listed). It allows you to specify the dragged and dropped elements, the offset to use for both, coordinates as per this offset, and whether to use pixels or percentage.
salesTable.BodyRows[3].Cells[1].DragTo(ArtOfTest.Common.OffsetReference.AbsoluteCenter, 0, 0, true, salesTable.BodyRows[2].Cells[1], ArtOfTest.Common.OffsetReference.AbsoluteCenter, 0, 0, true)
  
// Verify the new row subtotals are correct
Assert.AreEqual(salesTable.Rows[2].Cells[5].TextContent, "$3342.78");
Assert.AreEqual(salesTable.Rows[3].Cells[5].TextContent, "$2175.17");
```
```VB
' Find the sales table
Dim salesTable As HtmlTable = Find.ById(Of HtmlTable)("area_1_table")
  
' Drag the data from row 4 to row 3
salesTable.BodyRows(3).Cells(1).DragTo(salesTable.BodyRows(2).Cells(1))
  
' Verify the new row subtotals are correct
Assert.AreEqual(salesTable.Rows(2).Cells(5).TextContent, "$3342.78")
Assert.AreEqual(salesTable.Rows(3).Cells(5).TextContent, "$2175.17")
```
