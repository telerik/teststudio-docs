---
title: Common HTML Find Expressions
page_title: Common HTML Find Expressions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/common-find-expressions.aspx, /user-guide/code-samples/html/common-find-expressions
position: 1
---
#Common HTML Find Expressions#

*I would like to click on a hyperlink based on its text value. I prefer to do this in code and not by editing an existing element's <a href="/features/elements-explorer/find-element" target="_blank">Find Settings</a>*.

##Solution##

Let's use <a href="http://www.wikipedia.org/" target="_blank">wikipedia.org</a> as an example. First we'll find and click the top bold English link.

![wikipedia][1]

Here's the HTML code for that link:

```HTML
<a href="//en.wikipedia.org/" title="English — Wikipedia — The Free Encyclopedia">
<strong>English</strong>
<br>
<em>The Free Encyclopedia</em>
<br>
<small>3 907 000+ articles</small>
</a>
```

The anchor element has no direct TextContent, so we'll need to locate by a partial match on InnerText:

```C#
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("InnerText=~English", "tagname=a");
Assert.IsNotNull(a);
a.Click();
```

```VB
Dim a As HtmlAnchor = Find.ByExpression(Of HtmlAnchor)("InnerText=~English", "tagname=a")
Assert.IsNotNull(a)
a.Click()
```

If we locate by an exact match on TextContent, the bottom *English* link will found.

![english link][2]

Here's the HTML code for that link:

```HTML
<a href="//en.wikipedia.org/" lang="en">English</a>
```

Here's how to locate and click that link:

```C#
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("TextContent=English", "tagname=a");
Assert.IsNotNull(a);
a.Click();
```
```VB
Dim a As HtmlAnchor = Find.ByExpression(Of HtmlAnchor)("TextContent=English", "tagname=a")
Assert.IsNotNull(a)
a.Click()
```

The following attributes apply to both links, however Test Studio returns the first HtmlAnchor that matches. In this case, that's the top bold *English* link.

```C#
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("tagname=a", "href=//en.wikipedia.org/");
```
```VB
Dim a As HtmlAnchor = Find.ByExpression(Of HtmlAnchor)("tagname=a", "href=//en.wikipedia.org/")
```

You can find it by xpath:

```C#
HtmlAnchor a = Find.ByXPath<HtmlAnchor>("//*[@id=\"www-wikipedia-org\"]/div[5]/div/a[2]");
```
```VB
Dim a As HtmlAnchor = Find.ByXPath(Of HtmlAnchor)("//*[@id=""www-wikipedia-org""]/div[5]/div/a[2]")
```

You can also data drive the find expression:

```C#
HtmlAnchor a = Find.ByExpression<HtmlAnchor>("tagname=a", "textcontent=" + Data["Col1"].ToString());
```
```VB
Dim a As HtmlAnchor = Find.ByExpression(Of HtmlAnchor)("tagname=a", "textcontent=" + Data("Col1").ToString())
```


[1]: /img/advanced-topics/coded-samples/html/common-find-expressions/fig1.png
[2]: /img/advanced-topics/coded-samples/html/common-find-expressions/fig2.png



