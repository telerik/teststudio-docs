---
title: Extract an Attribute
page_title: Extract an Attribute
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/extract-an-attribute.aspx, /user-guide/code-samples/html/extract-an-attribute
position: 1
---
# Extract an Individual HTML Attribute

*I would like to extract an individual HTML attribute and use it later in the test.*

## Solution

This is possible with a coded solution. First, be aware that if you're simply verifying the value for a specific attribute, that can be accomplished without code using an <a href="/features/verifications/advanced-verification" target="_blank">Advanced Verification</a>.

HTML elements are formatted the following way:

```
<tagname attribute="value">content</tagname>
```


```HTML
<a href="http://www.google.com" lang="en" id="googleLink">Go to Google</a>
```


Here's how to set the value of the *lang* attribute (*which is en*) to a string. That string is then set as an <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">extracted value</a> to use later in the test through data binding (either attached to an <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">input value</a> or a <a href="/features/data-driven-testing/attach-columns-verifications" target="_blank">verification</a>).

```C#
HtmlAnchor a = Find.ById<HtmlAnchor>("googleLink");
Assert.IsNotNull(a);
 
string atr = a.Attributes.Single(x => x.Name == "lang").Value;
Log.WriteLine(atr);
SetExtractedValue("extraction", atr);
```
```VB
Dim a As HtmlAnchor = Find.ById(Of HtmlAnchor)("googleLink")
Assert.IsNotNull(a)
 
Dim atr As String = a.Attributes.[Single](Function(x) x.Name = "lang").Value
Log.WriteLine(atr)
SetExtractedValue("extraction", atr)
```