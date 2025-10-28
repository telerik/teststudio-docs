---
title: Verify Style
page_title: Verify Style
description: "Learn how to verify and extract HTML element styles in Test Studio using C# and VB.NET. This guide provides a coded solution for style verification and data extraction to enhance automated testing workflows."
previous_url: /user-guide/code-samples/html/verify-style.aspx, /user-guide/code-samples/html/verify-style
position: 1
---
# Verify HTML Style 

*I would like to verify an HTML element's style and extract it for use later in the test.*

## Solution

This is possible with a coded solution. First, be aware that if you're simply verifying a style, that can be accomplished without code using an <a href="/features/verifications/advanced-verification" target="_blank">Advanced Verification</a>.

The example below is against <a href="http://www.w3schools.com/html/tryit.asp?filename=tryhtml_styles_font-family" target="_blank">this W3Schools site</a>. Two styles are verified, retrieved as strings, and set as <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">extracted values</a> to use later in the test through data binding (either attached to an <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">input value</a> or a <a href="/features/data-driven-testing/attach-columns-verifications" target="_blank">verification</a>).

```C#
Browser frame = ActiveBrowser.Frames["view"];
HtmlControl paragraph = frame.Find.ByTagIndex<HtmlControl>("p", 0);
Assert.IsNotNull(paragraph);
 
string family = paragraph.Styles.Get("font-family");
Log.WriteLine(family);
SetExtractedValue("familyVar", family);
 
string color = paragraph.Styles.Get("color");
Log.WriteLine(color);
SetExtractedValue("colorVar", color);
 
paragraph.AssertStyle().Font(HtmlStyleFont.Family, "verdana", HtmlStyleType.Computed, StringCompareType.Exact);
paragraph.AssertStyle().ColorAndBackground(HtmlStyleColorAndBackground.Color, "#FF0000", HtmlStyleType.Computed, StringCompareType.Exact);
```
```VB
Dim frame As Browser = ActiveBrowser.Frames("view")
Dim paragraph As HtmlControl = frame.Find.ByTagIndex(Of HtmlControl)("p", 0)
Assert.IsNotNull(paragraph)
 
Dim family As String = paragraph.Styles.[Get]("font-family")
Log.WriteLine(family)
SetExtractedValue("familyVar", family)
 
Dim color As String = paragraph.Styles.[Get]("color")
Log.WriteLine(color)
SetExtractedValue("colorVar", color)
 
paragraph.AssertStyle().Font(HtmlStyleFont.Family, "verdana", HtmlStyleType.Computed, StringCompareType.Exact)
paragraph.AssertStyle().ColorAndBackground(HtmlStyleColorAndBackground.Color, "#FF0000", HtmlStyleType.Computed, StringCompareType.Exact)
```