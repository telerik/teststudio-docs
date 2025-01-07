---
title: Element Styles
page_title: Element Styles
description: "Test Studio Testing Framework read and validate the styles of HTML elements in coded tests."
position: 2
---
#Element Styles and HtmlStyle, GetStyle, GetComputedStyle

Telerik Testing Framework includes a good set of classes and methods for reading and validating the styles often attached to HTML controls. With this feature you can do things like:

* Get a particular style and value from an element.

* Get the cascaded style and value from an element.

* Validate the color of a control.

* Validate the margin setting of a control.

* Convert an HTML color to a .NET ARGB color object.

* Determine if the value of a style is a color.

* Determine if the value of a style is an integer.
 
Let's look at some code samples to see how this works:

```C#
// Verify the color of the warning text is Red
HtmlSpan warningSpan = Find.ById<HtmlSpan>("Warning");
HtmlStyle warningColorStyle = warningSpan.GetStyle("color");
  
// Verify the style's value is a color value.
// In reality it's not necessary to test using both IsColor and IsInt.
// The Color objects are converted to ARGB in case the element style uses an RGB triplet or hexadecimal format.
Assert.IsTrue(warningColorStyle.IsColor());
Assert.IsFalse(warningColorStyle.IsInt());
Color warningColor = warningColorStyle.ToColor();
Assert.AreEqual(Color.Red.ToArgb(), warningColor.ToArgb());
  
// If we don't want to use Assert, we can use IsSameColor instead.
if (!HtmlStyle.IsSameColor(Color.Red, warningColor))
{
    Log.WriteLine(LogType.Error, string.Format("Warning color is not red. It is {0}", warningColor.ToString()));
}
  
// We have the option of converting a .NET Color object into an HTML color string
string htmlColorString = HtmlStyle.ToHtmlColor(Color.SaddleBrown);
htmlColorString = HtmlStyle.ToHtmlColor(Color.FromArgb(33, 44, 55));
  
// Let's log the name and value of all the styles attached to this element
foreach (string strStyle in warningSpan.Styles)
{
    HtmlStyle aStyle = warningSpan.GetStyle(strStyle);
    Log.WriteLine(LogType.Information, string.Format("Style name: {0}, Style Value {1}",
        aStyle.Name, aStyle.Value));
}
  
// Verify the margin is set to 30 units (but note we don't know what the unit of measure is)
HtmlStyle warningMarginStyle = warningSpan.GetStyle("margin");
Assert.IsTrue(warningMarginStyle.IsInt());
int warningMargin = warningMarginStyle.ToInt();
Assert.AreEqual(30, warningMargin);
```
```VB
' Verify the color of the warning text is Red
Dim warningSpan As HtmlSpan = Find.ById(Of HtmlSpan)("Warning")
Dim warningColorStyle As HtmlStyle = warningSpan.GetStyle("color")
  
' Verify the style's value is a color value.
' In reality it's not necessary to test using both IsColor and IsInt.
' They're both used here for demonstration purposes only.
Assert.IsTrue(warningColorStyle.IsColor())
Assert.IsFalse(warningColorStyle.IsInt())
Dim warningColor As Color = warningColorStyle.ToColor()
Assert.AreEqual(Color.Red.toArgb(), warningColor.toArgb())
  
' If we don't want to use Assert, we can use IsSameColor instead.
If Not HtmlStyle.IsSameColor(Color.Red, warningColor) Then
    Log.WriteLine(LogType.Error, String.Format("Warning color is not red. It is {0}", warningColor.ToString()))
End If
  
' We have the option of converting a .NET Color object into an HTML color string
Dim htmlColorString As String = HtmlStyle.ToHtmlColor(Color.SaddleBrown)
htmlColorString = HtmlStyle.ToHtmlColor(Color.FromArgb(33, 44, 55))
  
' Let's log the name and value of all the styles attached to this element
For Each strStyle As String In warningSpan.Styles
    Dim aStyle As HtmlStyle = warningSpan.GetStyle(strStyle)
    Log.WriteLine(LogType.Information, String.Format("Style name: {0}, Style Value {1}", _
       aStyle.Name, aStyle.Value))
Next
  
' Verify the margin is set to 30 units (but note we don't know what the unit of measure is)
Dim warningMarginStyle As HtmlStyle = warningSpan.GetStyle("margin")
Assert.IsTrue(warningMarginStyle.IsInt())
Dim warningMargin As Integer = warningMarginStyle.ToInt()
Assert.AreEqual(30, warningMargin)
```

The GetComputedStyle is especially powerful. It will follow the CSS chain up through all the parent elements until it finds the first matching style and returns the value picked up from that style. This is quite different from GetStyle which only returns an explicitly set style value on the specific element (i.e. it does not follow the CSS chain). If no explicit value has been set then GetStyle returns an empty string for the value. 

Here's an example:

```C#
// GetStyle returns the value of an explicit style applied to the element.
// If the element does not have an explicit style applied, GetStyle returns an empty value.
// Since our warning span does not have the padding style explicitly applied to it,
// GetStyle returns a style with an empty value.
HtmlStyle paddingStyle = warningSpan.GetStyle("padding");
Assert.IsTrue(string.IsNullOrEmpty(paddingStyle.Value));
  
// However GetComputedStyle will follow the CSS until it finds the currently active style value.
// Our warning span is contained within a form that has a padding style.
// Therefore GetComputedStyle on the warning span will return the value set in the parent form tag.
paddingStyle = warningSpan.GetComputedStyle("padding");
Assert.IsFalse(string.IsNullOrEmpty(paddingStyle.Value));
```
```VB
' GetStyle returns the value of an explicit style applied to the element.
' If the element does not have an explicit style applied, GetStyle returns an empty value.
' Since our warning span does not have the padding style explicitly applied to it,
' GetStyle returns a style with an empty value.
Dim paddingStyle As HtmlStyle = warningSpan.GetStyle("padding")
Assert.IsTrue(String.IsNullOrEmpty(paddingStyle.Value))
  
' However GetComputedStyle will follow the CSS until it finds the currently active style value.
' Our warning span is contained within a form that has a padding style.
' Therefore GetComputedStyle on the warning span will return the value set in the parent form tag.
paddingStyle = warningSpan.GetComputedStyle("padding")
Assert.IsFalse(String.IsNullOrEmpty(paddingStyle.Value))
```