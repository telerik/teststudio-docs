---
title: HTML Asserts
page_title: HTML Asserts
description: "Test Studio Testing Framework validate an HTML element identified in the DOM in coded tests. HTML asserts to perform on an element in coded tests."
position: 2
---
# HTML Asserts

Telerik Testing Framework has a set of Assert classes to make validation of your HTML controls easier. An 'Assert' basically says "Verify the specified property of the control has the specified value or setting. If it doesn't have that setting/value, then throw an error and stop the test." 

For example: AssertCheck.IsTrue() will verify the associated checkbox control is checked. If it isn't the framework will throw an assert exception and stop the test. If it is the test will simply continue to the next step. Nothing else happens for Asserts that pass validation.

<table class="docs">
<tr>
	<th>Assert Class</th><th>Class Description</th><th>Assert method</th><th>Method Description</th>
</tr>
<tr>
	<td rowspan="2">AssertAttribute</td>
	<td rowspan="2">Validates the properties of an attribute.</td>
	<td>Value</td>
	<td>Checks the string value of the specified attribute. Asserts if the expected value was not found.</td>
</tr>
<tr>
	<td>Exists</td>
	<td>Asserts if the specified attribute does not exist for this element.</td>
</tr>
<tr>
	<td rowspan="2">AssertCheck</td>
	<td rowspan="2">Validates the checked state of check boxes and radio buttons.</td>
	<td>IsFalse</td>
	<td>Asserts if the control is checked.</td>
</tr>
<tr>
	<td>IsTrue</td>
	<td>Asserts if the control is not checked.</td>
</tr>
<tr>
	<td rowspan="5">AssertContent</td>
	<td rowspan="5">Validates the content of an HtmlControl.</td>
	<td>InnerMarkup</td>
	<td>Asserts if the inner HTML of the control does not match.</td>
</tr>
<tr>
	<td>InnerText</td>
	<td>Asserts if the inner text of the control does not match.</td>
</tr>
<tr>
	<td>OuterMarkup</td>
	<td>Asserts if the outer HTML of the control does not match.</td>
</tr>
<tr>
	<td>StartTagContent</td>
	<td>Asserts if the value of the tag for this HTML control does not match.</td>
</tr>
<tr>
	<td>TextContent</td>
	<td>Asserts if the text content of the HTML control does not match.</td>
</tr>
<tr>
	<td rowspan="8">AssertSelect</td>
	<td rowspan="8">Validates the various properties of an HtmlSelect.</td>
	<td>ItemsCountIs</td>
	<td>Asserts if the total number of items in the list does not match the expected value.</td>
</tr>
<tr>
	<td>SelectedIndex</td>
	<td>Asserts if the index value of the currently selected item does not match the expected value.</td>
</tr>
<tr>
	<td>SelectedText</td>
	<td>Asserts if the text of the currently selected item does not match the expected value.</td>
</tr>
<tr>
	<td>SelectedValue</td>
	<td>Asserts if the value of the currently selected item does not match the expected value.</td>
</tr>
<tr>
	<td>TextExists</td>
	<td>Asserts if the expected value was not found in the list of text's to display for this control.</td>
</tr>
<tr>
	<td>TextExistsNot</td>
	<td>Asserts if the expected value not found in the list of text's to display for this control.</td>
</tr>
<tr>
	<td>ValueExists</td>
	<td>Asserts if the expected value was not found in the list of values for the items in this control.</td>
</tr>
<tr>
	<td>ValueExistsNot</td>
	<td>Asserts if the expected value not found in the list of values for the items in this control.</td>
</tr>
<tr>
	<td rowspan="6">AssertStyle</td>
	<td rowspan="6">Validates the various common styles of an HtmlControl.</td>
	<td>Box</td>
	<td>Asserts if a particular box style does not match (e.g. margin, border, padding).</td>
</tr>
<tr>
	<td>ColorAndBackground</td>
	<td>Asserts if a particular color or background style does not match (e.g. background color, background image, etc.) NOTE: AssertStyle.ColorAndBackground() automatically detects colors and will perform the proper validation regardless of the format of the color encoding attached to the style e.g. "red" will match "#FF0000".</td>
</tr>
<tr>
	<td>Display</td>
	<td>Asserts if a particular display style does not match (e.g. width, height, display, position, etc.)</td>
</tr>
<tr>
	<td>Font</td>
	<td>Asserts if a particular font style does not match (e.g. family, variant, size, etc.)</td>
</tr>
<tr>
	<td>List</td>
	<td>Asserts if a particular list style does not match (e.g. type, image, position, etc.)</td>
</tr>
<tr>
	<td>Text</td>
	<td>Asserts if a particular text style does not match (e.g. word spacing, letter spacing, text align, etc.)</td>
</tr>
<tr>
	<td rowspan="5">AssertTable</td>
	<td rowspan="5">Validates the common properties of an HtmlTable control.</td>
	<td>ColumnCount</td>
	<td>Asserts if the number of columns does not match the expected value.</td>
</tr>
<tr>
	<td>ColumnRange</td>
	<td>Asserts if the number of columns is not inside or not outside of the specified range.</td>
</tr>
<tr>
	<td>Contains</td>
	<td>Asserts if the table contains/does not contain the expected value.</td>
</tr>
<tr>
	<td>RowCount</td>
	<td>Asserts if the number of rows does not match the expected value.</td>
</tr>
<tr>
	<td>RowRange</td>
	<td>Asserts if the number of rows is not inside or not outside of the specified range.</td>
</tr>
</table>

Now let's see how this works in action:

````C#
// Attribute checks
HtmlSpan span = Find.ById<HtmlSpan>("Warning");
span.AssertAttribute().Exists("style");
span.AssertAttribute().Value("style", ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "color");
  
// Checkbox checks
HtmlInputCheckBox cbx = Find.ById<HtmlInputCheckBox>("Checkbox1");
cbx.AssertCheck().IsTrue();
cbx.Click();
cbx.AssertCheck().IsFalse();
  
// Content checks
span.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "Warning");
span.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.NotContain, "Error");
span.AssertContent().StartTagContent(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.StartsWith, "<span");
  
HtmlDiv topdiv = Find.ById<HtmlDiv>("topmost");
topdiv.AssertContent().TextContent(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most text");
topdiv.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most textMiddle level textInnermost text");
topdiv.AssertContent().OuterMarkup(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "<DIV id=topmost>Top most text<DIV id=middle>Middle level text<DIV id=innermost>Innermost text</DIV></DIV></DIV>");
topdiv.AssertContent().InnerMarkup(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most text<DIV id=middle>Middle level text<DIV id=innermost>Innermost text</DIV></DIV>");
  
// Select checks
HtmlSelect select = Find.ById<HtmlSelect>("color_product");
select.AssertSelect().ItemsCountIs(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 5);
select.AssertSelect().SelectedIndex(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 0);
select.AssertSelect().SelectedText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Color : Blue");
select.AssertSelect().SelectedValue(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Blue");
  
select.SelectByIndex(3);
select.AssertSelect().SelectedIndex(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3);
select.AssertSelect().SelectedText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Color : Orange");
select.AssertSelect().SelectedValue(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Orange");
  
select.AssertSelect().TextExists("Color : Black");
select.AssertSelect().TextExistsNot("Color : Magenta");
select.AssertSelect().ValueExists("Black");
select.AssertSelect().ValueExistsNot("Magenta");
  
// Style checks
NameValueCollection styles = span.Styles;
span.AssertStyle().Font(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleFont.Style, "italic");
span.AssertStyle().Text(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleText.TextAlign, "right");
span.AssertStyle().ColorAndBackground(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleColorAndBackground.Color, "red",
    ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleType.Computed,
    ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact);
  
// Table checks
HtmlTable table = Find.ById<HtmlTable>("outertable1");
table.AssertTable().ColumnCount(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3);
table.AssertTable().ColumnRange(ArtOfTest.Common.NumberRangeCompareType.InRange, 2, 5);
table.AssertTable().RowCount(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3);
table.AssertTable().RowRange(ArtOfTest.Common.NumberRangeCompareType.OutsideRange, 1, 2);
table.AssertTable().Contains(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "TD5");
table.AssertTable().Contains(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.NotContain, "TD37");
````
````VB
' Attribute checks
Dim span As HtmlSpan = Find.ById(Of HtmlSpan)("Warning")
span.AssertAttribute().Exists("style")
span.AssertAttribute().Value("style", ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "color")
  
' Checkbox checks
Dim cbx As HtmlInputCheckBox = Find.ById(Of HtmlInputCheckBox)("Checkbox1")
cbx.AssertCheck().IsTrue()
cbx.Click()
cbx.AssertCheck().IsFalse()
  
' Content checks
span.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "Warning")
span.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.NotContain, "Error")
span.AssertContent().StartTagContent(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.StartsWith, "<span")
  
Dim topdiv As HtmlDiv = Find.ById(Of HtmlDiv)("topmost")
topdiv.AssertContent().TextContent(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most text")
topdiv.AssertContent().InnerText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most textMiddle level textInnermost text")
topdiv.AssertContent().OuterMarkup(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "<DIV id=topmost>Top most text<DIV id=middle>Middle level text<DIV id=innermost>Innermost text</DIV></DIV></DIV>")
topdiv.AssertContent().InnerMarkup(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Top most text<DIV id=middle>Middle level text<DIV id=innermost>Innermost text</DIV></DIV>")
   
' Select checks
Dim [select] As HtmlSelect = Find.ById(Of HtmlSelect)("color_product")
[select].AssertSelect().ItemsCountIs(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 5)
[select].AssertSelect().SelectedIndex(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 0)
[select].AssertSelect().SelectedText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Color : Blue")
[select].AssertSelect().SelectedValue(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Blue")
  
[select].SelectByIndex(3)
[select].AssertSelect().SelectedIndex(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3)
[select].AssertSelect().SelectedText(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Color : Orange")
[select].AssertSelect().SelectedValue(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact, "Orange")
  
[select].AssertSelect().TextExists("Color : Black")
[select].AssertSelect().TextExistsNot("Color : Magenta")
[select].AssertSelect().ValueExists("Black")
[select].AssertSelect().ValueExistsNot("Magenta")
  
' Style checks
Dim styles As NameValueCollection = span.Styles
span.AssertStyle().Font(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleFont.Style, "italic")
span.AssertStyle().Text(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleText.TextAlign, "right")
span.AssertStyle().ColorAndBackground(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleColorAndBackground.Color, "red", ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.HtmlStyleType.Computed, ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Exact)
  
' Table checks
Dim table As HtmlTable = Find.ById(Of HtmlTable)("outertable1")
table.AssertTable().ColumnCount(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3)
table.AssertTable().ColumnRange(ArtOfTest.Common.NumberRangeCompareType.InRange, 2, 5)
table.AssertTable().RowCount(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.NumberCompareType.Equals, 3)
table.AssertTable().RowRange(ArtOfTest.Common.NumberRangeCompareType.OutsideRange, 1, 2)
table.AssertTable().Contains(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.Contains, "TD5")
table.AssertTable().Contains(ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts.StringCompareType.NotContain, "TD37")
````


There are many other possible assert verification combinations built into the framework that you can take advantage of. The above examples are just a small subset of what is possible to help you get started implementing them in your code and crafting the kinds of verification you need for your particular website. Consult the API reference manual to learn about the other combinations.


