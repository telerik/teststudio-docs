---
title: Partial Attributes Search Fails
page_title: Partial Attributes Search Fails
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/search-control-type-by-partial-attributes-fails.aspx, /user-guide/code-samples/html/search-control-type-by-partial-attributes-fails
position: 1
---
# Partial Attributes Search by Control Type Fails

## PROBLEM

A partial search of control by attribute may return null even with correct partial search syntax. For example a HtmlInputButton search on the page having a complex ID containing some specific string should be located successfully using the following syntax:

```C#
HtmlInputButton button = Find.ById<HtmlInputButton>("~MyButtonIDPart");
```


Although the next example works:


```C#
HtmlInputButton button = Find.ById<HtmlInputButton>("SomeButtonIDPart_MyButtonIDPart");
```

## DESCRIPTION

The framework locates the first element matching the given attribute search criteria. Next, it compares the control type of the element and returns that element if the control type matches. If it does not, it simply returns null.
 
In the first example, the framework returns null if there is another element that matches the given attribute search criteria and it is found before the target element. The control type does not match.

## Solution

A simple solution is available. Use Find.AllByAttributes<Control Type> overload and return the first (and actually the only completely matching control):

```C#
HtmlInputButton button = Find.AllByAttributes<HtmlInputButton>("id=~MyButtonIDPart")[0];
```



