---
title: HTML Actions
page_title: HTML Actions | Test Studio Dev Documentation
description: HTML Actions 
position: 2
---
#Common HTML Control Actions#

What are some of the things we can do after finding the element we want to act upon? We can:

* Click on elements

* Perform mouse actions on elements

* Check/uncheck radio buttons and checkboxes

* Invoke events such as OnClick, OnFocus

* Capture an image snapshot

* Make selections of a drop down
 
Here are some examples:

#### __[C#]__

          {{region }}

    // All controls have a Click/MouseClick. The .Click invokes a click from the DOM,
    // the MouseClick(), moves the mouse to the control and clicks it.
    
    //
    // CLICKING
    //
    Find.ById<HtmlInputButton>("button1").Click();
    ActiveBrowser.Refresh();
    Find.ById<HtmlInputButton>("button1").MouseClick();
    
    // You can capture any element on the page using the .Capture()
    Find.ById<HtmlInputImage>("image1").Capture("myfile"); // Will be stored to the Log.LogLocation
    
    //
    // CHECKING
    //
    // Check a checkbox and invoke the onclick event.
    HtmlInputCheckBox ck = Find.ById<HtmlInputCheckBox>("checkbox1");
    ck.Check(true, true);
    
    // Query the checked state
    Assert.IsTrue(ck.Checked);
    // You can also simply set the value without invoking the clicked event.
    ck.Checked = false;
    Assert.IsFalse(ck.Checked);
    
    // Get whether a checkbox is enabled or disabled.
    HtmlInputCheckBox cks = Find.ById<HtmlInputCheckBox>("checkbox1");
    bool disabled = cks.GetValue<bool>("disabled");
    
    // Disable it
    cks.SetValue<bool>("disabled", true);
    Assert.IsTrue(cks.GetValue<bool>("disabled"));
    
    // Is it visible
    Assert.IsTrue(cks.IsVisible());
    
    // When the contents of a div element are larger than the declared
    // width or height of element it automatically adds scroll bars.
    // When that happens we can scroll the contents of the div element.
    // The value represents the offset in pixels to scroll the contents.
    HtmlDiv infoDiv = Find.ById<HtmlDiv>("AutoInfo");
    infoDiv.ScrollTop = 50;
    infoDiv.ScrollLeft = 75;
    
    // Get the color style
    HtmlSpan mySpan = Find.ById<HtmlSpan>("Warning");
    HtmlStyle styleColor = mySpan.GetStyle("color");
    string strColor = mySpan.GetStyleValue("color");
    
    // Getting the computed style will follow the CSS chain and return the
    // style.
    HtmlStyle styleMargin = mySpan.GetComputedStyle("margin");
    string strMargin = mySpan.GetComputedStyleValue("margin");
    
    //
    // SELECTING
    //
    HtmlSelect select = Find.ById<HtmlSelect>("select1");
    Assert.IsTrue(select.SelectedOption.Value.Equals("Option1Text"));
    Assert.IsTrue(select.SelectedOption.Text.Equals("Option1"));
    Assert.IsTrue(select.SelectedIndex.Equals(0));
    
    select.SelectByIndex(1);
    Assert.IsTrue(select.SelectedOption.Text.Equals("Option2"));
    
    //
    // MULTI-SELECTING
    //
    HtmlSelect multi_select = Find.ById<HtmlSelect>("select2");
    multi_select.MultiSelectByText("E3145", "R4325", "W4573", "L5623");
    multi_select.MultiSelectByValue("E3145", "R4325", "W4573", "L5623");
    
    HtmlOption opt0 = multi_select.Options[0];
    HtmlOption opt2 = multi_select.Options[2];
    HtmlOption opt4 = multi_select.Options[4];
    multi_select.MultiSelect(opt0, opt2, opt4);
    
    //
    // SET TEXT
    //
    Find.ById<HtmlTextArea>("textarea1").Text = "NEW TEXT";
    
    // Access common methods
    HtmlAnchor link = Find.ByAttributes<HtmlAnchor>("href=~google");
    Assert.IsTrue(link.Attributes.Count == 3);
    Assert.IsTrue(link.BaseElement.TextContent.Trim().Equals("Link"));
    
    // Invoke any events on the control
    link.InvokeEvent(ScriptEventType.OnFocus);
    {{endregion}}
 

#### __[VB]__

          {{region }}

    ' All controls have a Click/MouseClick. The .Click invokes a click from the DOM,
    ' the MouseClick(), moves the mouse to the control and clicks it.   
    
    '
    ' CLICKING
    '
    Find.ById(Of HtmlInputButton)("button1").Click()
    ActiveBrowser.Refresh()
    Find.ById(Of HtmlInputButton)("button1").MouseClick()
        
    ' You can capture any element on the page Imports the .Capture()
    Find.ById(Of HtmlInputImage)("image1").Capture("myfile")    ' Will be stored to the Log.LogLocation
        
    '
    ' CHECKING  
    '
    ' Check a checkbox and invoke the onclick event.   
    Dim ck As HtmlInputCheckBox = Find.ById(Of HtmlInputCheckBox)("checkbox1")
    ck.Check(True, True)    
    
    ' Query the checked state
    Assert.IsTrue(ck.Checked)   
    ' You can also simply set the value without invoking the clicked event.
    ck.Checked = False  
    Assert.IsFalse(ck.Checked)
        
    ' Get whether a checkbox is enabled or disabled.
    Dim cks As HtmlInputCheckBox = Find.ById(Of HtmlInputCheckBox)("checkbox1")   
    Dim disabled As Boolean = cks.GetValue(Of Boolean)("disabled")   
    
    ' Disable it
    cks.SetValue(Of Boolean)("disabled", True)   
    Assert.IsTrue(cks.GetValue(Of Boolean)("disabled"))
    
    ' Is it visible   
    Assert.IsTrue(cks.IsVisible())
        
    ' When the contents of a div element are larger than the declared
    ' width or height of element it automatically adds scroll bars.   
    ' When that happens we can scroll the contents of the div element.
    ' The value represents the offset in pixels to scroll the contents.   
    Dim infoDiv As HtmlDiv = Find.ById(Of HtmlDiv)("AutoInfo")
    infoDiv.ScrollTop = 50   
    infoDiv.ScrollLeft = 75
        
    ' Get the color style
    Dim mySpan As HtmlSpan = Find.ById(Of HtmlSpan)("Warning")   
    Dim styleColor As HtmlStyle = mySpan.GetStyle("color")
    Dim strColor As String = mySpan.GetStyleValue("color")
        
    ' Getting the computed style will follow the CSS chain and return the
    ' style.   
    Dim styleMargin As HtmlStyle = mySpan.GetComputedStyle("margin")
    Dim strMargin As String = mySpan.GetComputedStyleValue("margin")
        
    '
    ' SELECTING 
    '  
    Dim select1 As HtmlSelect = Find.ById(Of HtmlSelect)("select1")   
    Assert.IsTrue(select1.SelectedOption.Value.Equals("Option1Text"))   
    Assert.IsTrue(select1.SelectedOption.Text.Equals("Option1"))   
    Assert.IsTrue(select1.SelectedIndex.Equals(0))
        
    select1.SelectByIndex(1)
    Assert.IsTrue(select1.SelectedOption.Text.Equals("Option2"))    
    
    '
    ' MULTI-SELECTING   
    '
    Dim multi_select As HtmlSelect = Find.ById(Of HtmlSelect)("select2")   
    multi_select.MultiSelectByText("E3145", "R4325", "W4573", "L5623")
    multi_select.MultiSelectByValue("E3145", "R4325", "W4573", "L5623")
        
    Dim opt0 As HtmlOption = multi_select.Options(0)   
    Dim opt2 As HtmlOption = multi_select.Options(2)
    Dim opt4 As HtmlOption = multi_select.Options(4)  
    multi_select.MultiSelect(opt0, opt2, opt4)
        
    '
    ' SET TEXT   
    '
    Find.ById(Of HtmlTextArea)("textarea1").Text = "NEW TEXT"
        
    ' Access common methods
    Dim link As HtmlAnchor = Find.ByAttributes(Of HtmlAnchor)("href=~google")   
    Assert.IsTrue(link.Attributes.Count = 3)
    Assert.IsTrue(link.BaseElement.TextContent.Trim().Equals("Link"))
        
    ' Invoke any events on the control
    link.InvokeEvent(ScriptEventType.OnFocus)
    {{endregion}}
