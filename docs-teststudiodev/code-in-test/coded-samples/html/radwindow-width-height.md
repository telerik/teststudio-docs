---
title: RadWindow Width & Height
page_title: RadWindow Width & Height - Test Studio Dev Documentation
description: RadWindow Width & Height
position: 1
---
# Getting RadWindow Width and Height #

*I need to get the RadWindow width or height property.*

## Solution ##

First you need to get a reference to the RadWindow control by ID. Once you get it there are two options for getting the width/height. The first option is to use the relevant width/height properties of the RadWindow. The second is by invoking a straight JavaScript on the page.

Here is the standard approach:

#### __[C#]__

    {{region }}

    Manager.LaunchNewBrowser();
    ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx");
    Find.ById<HtmlInputSubmit>("Button3").MouseClick();
    System.Threading.Thread.Sleep(1000);
    ActiveBrowser.RefreshDomTree();
    RadWindow window = Find.ById<RadWindow>("RadWindowWrapper_RadWindow_ContentTemplate");
    
    //First Option
    Assert.AreEqual(300, window.Width);
    {{endregion}}

#### __[VB]__

    {{region }}

    Manager.LaunchNewBrowser()
    ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx")
    Find.ById(Of HtmlInputSubmit)("Button3").MouseClick()
    System.Threading.Thread.Sleep(1000)
    ActiveBrowser.RefreshDomTree()
    Dim window As RadWindow = Find.ById(Of RadWindow)("RadWindowWrapper_RadWindow_ContentTemplate")

    Assert.AreEqual(300, window.Width)
    {{endregion}}

Invoking JavaScript on the page:

#### __[C#]__

    {{region }}

    Manager.LaunchNewBrowser();
    ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx");
    Find.ById<HtmlInputSubmit>("Button3").MouseClick();
    System.Threading.Thread.Sleep(1000);
    ActiveBrowser.RefreshDomTree();
    RadWindow window = Find.ById<RadWindow>("RadWindowWrapper_RadWindow_ContentTemplate"); 
    
    //Second Option
    string windowWidth = this.ActiveBrowser.Actions.InvokeScript(String.Format("$telerik.getBounds($find('RadWindow_ContentTemplate').get_popupElement()).width"));
    Assert.AreEqual("300", windowWidth);
    {{endregion}}

#### __[VB]__

    {{region }} 

    Manager.LaunchNewBrowser()
    ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/window/examples/contenttemplatevsnavigateurl/defaultcs.aspx")
    Find.ById(Of HtmlInputSubmit)("Button3").MouseClick()
    System.Threading.Thread.Sleep(1000)
    ActiveBrowser.RefreshDomTree()
    Dim window As RadWindow = Find.ById(Of RadWindow)("RadWindowWrapper_RadWindow_ContentTemplate")

    Dim windowWidth As String = Me.ActiveBrowser.Actions.InvokeScript([String].Format("$telerik.getBounds($find('RadWindow_ContentTemplate').get_popupElement()).width"))
    Assert.AreEqual("300", windowWidth)
    {{endregion}}


