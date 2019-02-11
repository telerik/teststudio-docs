---
title: Drag & Drop
page_title: Drag & Drop
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#How to Drag and Drop#

The HTML element wrapper classes make mouse drag & drop operations significantly easier. There are 7 different drag methods defined:

* public virtual void DragTo(*ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl* control)

* public virtual void DragTo(*System.Drawing.Point* absolutePoint)

* public virtual void DragTo(*int* offsetX, *int* offsetY)

* public virtual void DragTo(*ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl* control, 
*ArtOfTest.WebAii.Core.OffsetReference destinationOffsetReference*, *System.Drawing.Point* destinationOffset)

* public virtual void DragTo(*ArtOfTest.WebAii.Core.OffsetReference* sourceOffsetReference, *System.Drawing.Point* 

* sourceOffset, *ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl* destination)

* public virtual void DragTo(*ArtOfTest.WebAii.Core.OffsetReference* sourceOffsetReference, *System.Drawing.Point* 

* sourceOffset, int destinationOffsetX, int destinationOffsetY)

* public virtual void DragTo(*ArtOfTest.WebAii.Core.OffsetReference* sourceOffsetReference, *System.Drawing.Point* 

* sourceOffset, *ArtOfTest.WebAii.Controls.HtmlControls.HtmlControl* destination, *ArtOfTest.WebAii.Core.OffsetReference* destinationOffsetReference, *System.Drawing.Point* destinationOffset)


Suppose we have an sales by area table that supports drag & drop between cells. We can easily drag & drop the contents of one cell to another cell like this:

```C#
// Find the sales table
HtmlTable salesTable = Find.ById<HtmlTable>("area_1_table");
  
// Drag the data from row 4 to row 3
salesTable.BodyRows[3].Cells[1].DragTo(salesTable.BodyRows[2].Cells[1]);
  
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

