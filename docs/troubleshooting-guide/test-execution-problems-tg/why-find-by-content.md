---
title: Why Find.By.Content May Return Null
page_title: Why Find.By.Content May Return Null
description: "Understand why Find.ByContent may return null in Test Studio. This article explains common pitfalls, error scenarios, and provides solutions for locating elements by content in automated tests."
position: 1
---
# Why Find.By.Content May Return Null


## PROBLEM

I am looking for element by content, however the method returns NullReferenceException.

## SOLUTION

Find.ByContent finds the element by content then checks if the element matches and if it doesn't just returns null.
The solution is to call the method without specifying element type It will return the element the content matches for.

Example:

If we run the test against this html source:

	<div>Test</div>

The following find expression will return NullReferenceException:

```C#
HtmlAnchor elementName = ActiveBrowser.Find.ByContent<HtmlAnchor>("Test");
```
```VB
Dim elementName As HtmlAnchor = ActiveBrowser.Find.ByContent(Of HtmlAnchor)("Test")
```

The solution is to use either the correct element type:

```C#
HtmlDiv elementName = ActiveBrowser.Find.ByContent<HtmlDiv>("Test");
```
```VB
Dim elementName As HtmlDiv = ActiveBrowser.Find.ByContent(Of HtmlDiv)("Test")
```

or call the method without specifying element type: 

```C#
 Element a = ActiveBrowser.Find.ByContent("Test");
```
```VB
Dim a As Element = ActiveBrowser.Find.ByContent("Test")
```