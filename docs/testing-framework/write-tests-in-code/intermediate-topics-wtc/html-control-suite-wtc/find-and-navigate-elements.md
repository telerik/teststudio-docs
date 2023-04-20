---
title: Find and Navigate Elements
page_title: Find and Navigate Elements
description: "Test Studio Testing Framework finding elements in code and navigating through the DOM."
position: 2
---
#Finding and Navigating HTML Elements#

The example above used just two of the available find methods, the Find.ById<**TControl**> and the Find.AllByTagName<**TControl**> and did not take advantage of the powerful navigation features. Let's look at some other find examples:

```C#
// Find the first table on the page.
HtmlTable outertable = Find.ByTagIndex<HtmlTable>("table", 0);
  
// Find the first table inside the outer table
//
// Note: HtmlContainerControls have a Find object
//       associated with them that scopes all the Find.Byxx searches
//       to elements contained within them only.
//       So even if you have multiple controls with similar contained
//       elements, this will help avoid any conflicts.
//       Also, note how we are referencing the innertable using index 0
//       since it is the first table inside our outer table.
//
HtmlTable innerTable = outertable.Find.ByTagIndex<HtmlTable>("table", 0);
  
// Special Find for tables.
HtmlTableCell cell = innerTable.Find.TableCell("TD21");
Assert.IsTrue(cell.TextContent.Equals("TD21"));
  
// Find all HtmlInputImage controls with 'src' containing partial value 'logo'
IList<HtmlInputImage> imgCtrls = Find.AllByAttributes<HtmlInputImage>("src=~logo");
// There should only be one HtmlInputText control. All controls
// That match the attribute list but fail validation by the HtmlInputText control
// will be ignored.
Assert.AreEqual(1, imgCtrls.Count);
  
// Find the <div> section containing the Eastern US Division sales report
HtmlDiv EasternUSDivision = Find.ByContent<HtmlDiv>("Eastern US Division", FindContentType.TextContent);
Assert.IsNotNull(EasternUSDivision);
```
```VB
' Find the first table on the page.
Dim outertable As HtmlTable = Find.ByTagIndex(Of HtmlTable)("table", 0)
Assert.AreEqual(3, outertable.Rows.Count)
  
' Find the first table inside the outer table
'
' Note: HtmlContainerControls have a Find object 
'       associated with them that scopes all the Find.Byxx searches
'       to elements contained within them only. 
'       So even if you have multiple controls with similar contained
'       elements, this will help avoid any conflicts.
'       Also, note how we are referencing the innertable Imports index 0
'       since it is the first table inside our outer table.
'
Dim innerTable As HtmlTable = outertable.Find.ByTagIndex(Of HtmlTable)("table", 0)
  
' Special Find for tables. Find the first cell of the inner table that contains the text "TD21"
Dim cell As HtmlTableCell = innerTable.Find.TableCell("TD21")
Assert.IsTrue(cell.TextContent.Equals("TD21"))
   
' Find all HtmlInputImage controls with 'src' containing partial value 'logo'
Dim imgCtrls As IList(Of HtmlInputImage) = Find.AllByAttributes(Of HtmlInputImage)("src=~logo")
' There should only be one HtmlInputText control. All controls
' That match the attribute list but fail validation by the HtmlInputText control
' will be ignored.
Assert.AreEqual(1, imgCtrls.Count)
  
' Find the <div> section containing the Eastern US Division sales report
Dim EasternUSDivision As HtmlDiv = Find.ByContent(Of HtmlDiv)("Eastern US Division", FindContentType.TextContent)
Assert.IsNotNull(EasternUSDivision)
```


The above example demonstrates how to use many of the more useful find methods. There are many more. It would take up too much space to try and document them all here. Refer to the API reference to learn about the others. Let's look at some HTML navigation functions:

```C#
// Traverse the control tree upwards too. You can easily
// Find the container control of a certain type from its children.
  
// Find the owner form of the submit button
HtmlInputSubmit submitButton = Find.ById<HtmlInputSubmit>("submit");
HtmlForm form = submitButton.Parent<HtmlForm>();
  
// Get the name of the frame targeted by the form
string myFrame = form.Target;
Assert.AreEqual("_self", myFrame);
  
// Find the 3rd text input field on the form. Index is 0 based, so we enter 2 to mean the 3rd one.
HtmlInputText input = form.Find.ByTagIndex<HtmlInputText>("input", 2);
  
// Find the table that contains this cell.
HtmlTable table = cell.Parent<HtmlTable>();
Assert.IsTrue(table.ID.Equals(innerTable.ID));
  
// Find the parent table of this inner table.
HtmlTable table2 = table.Parent<HtmlTable>();
Assert.IsTrue(table2.ID.Equals(outertable.ID));
  
// Find the form this table is contained in.
HtmlForm form1 = table2.Parent<HtmlForm>();
Assert.IsTrue(form1.ID.Equals("form1"));
```
```VB
' Traverse the control tree upwards too. You can easily
' Find the container control of a certain type from its children.

' Find the owner form of the submit button
Dim submitButton As HtmlInputSubmit = Find.ById(Of HtmlInputSubmit)("submit")
Dim form As HtmlForm = submitButton.Parent(Of HtmlForm)()

' Get the name of the frame targeted by the form
Dim myFrame As String = form.Target
Assert.AreEqual("_self", myFrame)

' Find the 3rd text input field on the form. Index is 0 based, so we enter 2 to mean the 3rd one.
Dim input As HtmlInputText = form.Find.ByTagIndex(Of HtmlInputText)("input", 2)
Assert.IsNotNull(input)

' Find the table that contains this cell.
Dim table As HtmlTable = cell.Parent(Of HtmlTable)()
Assert.IsTrue(table.ID.Equals(innerTable.ID))

' Find the parent table of this inner table.
Dim table2 As HtmlTable = table.Parent(Of HtmlTable)()
Assert.IsTrue(table2.ID.Equals(outertable.ID))

' Find the form this table is contained in.
Dim form1 As HtmlForm = table2.Parent(Of HtmlForm)()
Assert.IsTrue(form1.ID.Equals("form1"))
```
