---
title: LINQ Queries
page_title: LINQ Queries
description: "Test Studio Testing Framework LINQ Queries"
position: 1
---


# LINQ Queries

The Find.Byxxx methods now support Language-Integrated Query (LINQ) queries. Some of the Find functions are intended to be used by LINQ queries only. These include:

<table class="docs">
<tr>
	<th>Methods</th><th>Description</th><th>Example</th>
</tr>
<tr>
	<td>**AllElements**</td>
	<td>Gets a IEnumerable for all elements to be used for LINQ queries.</td>
	<td>var inlineStyledElements = Find.AllElements().Where(element =><br>
	element.ContainsAttribute("style"));</td>
</tr>
<tr>
	<td>**AllControls**</td>
	<td>Gets an IEnumerable for TControl to be used for LINQ queries. This will return only elements that are convertible to TControl.</td>
	<td>var images = Find.AllControls<HtmlImage>();</td>
</tr>
<table>

Using LINQ we can create strongly typed advanced queries with intellisense support that we couldn't before. The most basic LINQ example is something like this:

````C#
// Find all images on a page.
var images = Find.AllControls<HtmlImage>();
 
foreach (HtmlImage img in images)
{
    // Do what you want with each img.
}
````


We can also use lambda expressions like this:

````C#
// Find the first element that contains "Go Google"
Element el = Find.ByCustom(e => e.TextContent.Contains("Go Google"));
  
// Find the first HTML anchor whose parent element does not have an input type
HtmlAnchor a = Find.ByCustom<HtmlAnchor>(e => e.BaseElement.InputElementType == InputElementType.NotSet);
Assert.IsNotNull(a);
  
// Find the first HTML anchor element that contains "Go Google"
HtmlAnchor l = Find.ByCustom<HtmlAnchor>(r => r.TextContent.Contains("Go Google"));
Assert.IsNotNull(l);
Assert.IsTrue(el.IdAttributeValue == "a0");
  
// Find the first HTML anchor element that contains "Go Google"
HtmlAnchor rr = (from b in Find.AllControls<HtmlAnchor>() where b.TextContent.Contains("Go Google") select b).First();
Assert.IsNotNull(rr);
  
// Fetch a list of HTML anchor's that contain 'a' in the ID
IList<HtmlAnchor> rd = (from b in Find.AllControls<HtmlAnchor>() where b.ID.Contains("a") select b).ToArray();
Assert.IsTrue(rd.Count > 0);
  
// Fetch a list of HTML anchor's that contain 'a' in the ID
IList<Element> li = (from b in Find.AllElements() where b.IdAttributeValue.Contains("a") select b).ToArray();
Assert.IsTrue(li.Count > 0);
````
