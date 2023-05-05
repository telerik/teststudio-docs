---
title: Get & Set Properties
page_title: Get & Set Properties
description: "Test Studio Testing Framework getting and setting properties of HTML elements in coded tests."
position: 2
---
#Getting and Setting Properties#

We can also get and set the current value of any property of the wrapped element:

```C#
// Get whether a checkbox is enabled or disabled.
HtmlInputCheckBox cks = Find.ById<HtmlInputCheckBox>("checkbox1");
bool disabled = cks.GetValue<bool>("disabled");
  
// Disable it
cks.SetValue<bool>("disabled", true);
Assert.IsTrue(cks.GetValue<bool>("disabled"));
  
// Is it visible. IsVisible follows the CSS chain to determine if the
// element is actually visible or not. An element is visible when
// the CSS the display style is not 'none' and the visibility style
// is not 'hidden'.
Assert.IsTrue(cks.IsVisible());
  
// Get the color style
HtmlSpan mySpan = Find.ById<HtmlSpan>("Warning");
HtmlStyle styleColor = mySpan.GetStyle("color");
string strColor = mySpan.GetStyleValue("color");
  
// Getting the computed style will follow the CSS chain and return the
// style.
HtmlStyle styleMargin = mySpan.GetComputedStyle("margin");
string strMargin = mySpan.GetComputedStyleValue("margin");
```
```VB
' Get whether a checkbox is enabled or disabled.
Dim cks As HtmlInputCheckBox = Find.ById(Of HtmlInputCheckBox)("checkbox1")
Dim disabled As Boolean = cks.GetValue(Of Boolean)("disabled")
  
' Disable it
cks.SetValue(Of Boolean)("disabled", True)
Assert.IsTrue(cks.GetValue(Of Boolean)("disabled"))
  
' Get the color style
Dim mySpan As HtmlSpan = Find.ById(Of HtmlSpan)("Warning")
Dim styleColor As HtmlStyle = mySpan.GetStyle("color")
Dim strColor As String = mySpan.GetStyleValue("color")
  
' Getting the computed style will follow the CSS chain and return the
' style.
Dim styleMargin As HtmlStyle = mySpan.GetComputedStyle("margin")
Dim strMargin As String = mySpan.GetComputedStyleValue("margin")
```