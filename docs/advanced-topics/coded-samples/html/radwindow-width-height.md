---
title: RadWindow Width & Height
page_title: RadWindow Width & Height
description: "Learn how to retrieve the width and height of a RadWindow in Test Studio using C#. This guide provides two approaches: accessing properties directly or invoking JavaScript for precise measurements during automated testing."
previous_url: /user-guide/code-samples/html/getting-radwindow-width-and-height.aspx, /user-guide/code-samples/html/getting-radwindow-width-and-height
position: 1
---
# Getting RadWindow Width and Height

*You need to get the RadWindow width or height property.*

## Solution

First you need to get a reference to the RadWindow control by ID. Once you get it there are two options for getting the width/height. The first option is to use the relevant width/height properties of the RadWindow. The second is by invoking a straight JavaScript on the page.

Here is the standard approach:

```C#
Manager.LaunchNewBrowser();
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx");
Find.ById<HtmlInputSubmit>("Button3").MouseClick();
System.Threading.Thread.Sleep(1000);
ActiveBrowser.RefreshDomTree();
RadWindow window = Find.ById<RadWindow>("RadWindowWrapper_RadWindow_ContentTemplate");
 
//First Option
Assert.AreEqual(300, window.Width);
```
```VB
Manager.LaunchNewBrowser()
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx")
Find.ById(Of HtmlInputSubmit)("Button3").MouseClick()
System.Threading.Thread.Sleep(1000)
ActiveBrowser.RefreshDomTree()
Dim window As RadWindow = Find.ById(Of RadWindow)("RadWindowWrapper_RadWindow_ContentTemplate")

Assert.AreEqual(300, window.Width)
```

Invoking JavaScript on the page:

```C#
Manager.LaunchNewBrowser();
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx");
Find.ById<HtmlInputSubmit>("Button3").MouseClick();
System.Threading.Thread.Sleep(1000);
ActiveBrowser.RefreshDomTree();
RadWindow window = Find.ById<RadWindow>("RadWindowWrapper_RadWindow_ContentTemplate"); 
 
//Second Option
string windowWidth = this.ActiveBrowser.Actions.InvokeScript(String.Format("$telerik.getBounds($find('RadWindow_ContentTemplate').get_popupElement()).width"));
Assert.AreEqual("300", windowWidth);
```
```VB
Manager.LaunchNewBrowser()
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx")
Find.ById(Of HtmlInputSubmit)("Button3").MouseClick()
System.Threading.Thread.Sleep(1000)
ActiveBrowser.RefreshDomTree()
Dim window As RadWindow = Find.ById(Of RadWindow)("RadWindowWrapper_RadWindow_ContentTemplate")

Dim windowWidth As String = Me.ActiveBrowser.Actions.InvokeScript([String].Format("$telerik.getBounds($find('RadWindow_ContentTemplate').get_popupElement()).width"))
Assert.AreEqual("300", windowWidth)
```