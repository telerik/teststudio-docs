---
title: Automate Browser Actions
page_title:  Automate Browser Actions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/getting-started/automating-browser-actions.aspx, /user-guide/getting-started/automating-browser-actions
position: 1
---
#Automate Browser Actions (DOM & UI)#

Telerik Testing Framework supports three types of automation actions:

* **Browser control**: Commands that make the browser perform an action. These actions are exposed using the Browser object. Each open window or frame is controlled by its own Browser object. This object lets you do things like Navigate to a URL, Go back, Go forward, Refresh, Wait until ready, Scroll window.

* **DOM automation**: Actions are executed directly against the DOM of the application being tested. All DOM actions are exposed using an 'Actions' object that is a property of each instantiated 'Browser' object. Some of the more common actions include Set Text, Check, Click, Select Drop Down, Scroll to Visible, Invoke Event, Invoke Script, Wait for Element.

* **Pure UI automation**: Actions are performed as true mouse/keyboard actions that simulate real user interactions. These actions are exposed using a 'Desktop' object that is a property of the 'Manager' object.
 
The code sample below demonstrates browser control and direct DOM actions.

```C#
// *** Browser control below
  
// Some test cases may require that all cookies be cleared ahead of time.  
// WebAii does not care but depending on your environment and your specific
// test case you may care.   
ActiveBrowser.ClearCache(ArtOfTest.WebAii.Core.BrowserCacheType.Cookies);
  
// Navigate to an explicit URL   
ActiveBrowser.NavigateTo("http://www.google.com");
    
// Navigate to a relative URL. The preceeding ~ means to use the
// baseURL setting stored in the app.config file   
ActiveBrowser.NavigateTo("~/videosearch");
  
// Let's check the title   
string pageTitle = ActiveBrowser.PageTitle;
Assert.AreEqual("Video Search Page", pageTitle, "Actual page title = \"{0}\"", pageTitle);    
  
// Backup to the previous web page
ActiveBrowser.GoBack();
  
// Return to the next web page after previous   
ActiveBrowser.GoForward();
  
// Refresh the current web page   
ActiveBrowser.Refresh();
  
// After performing a mouse click you may need to explicitly wait   
// for the browser to be ready. You very rarely would need to
// call this function when using the Actions methods.   
Desktop.Mouse.Click(MouseClickType.LeftClick, 300, 275);
ActiveBrowser.WaitUntilReady();
  
// Scroll the browser window in order to make some element visible   
ActiveBrowser.ScrollBy(225, 170);      // Scrolls right 220 and down 170 pixels
ActiveBrowser.ScrollBy(-225, -170);    // Scrolls left 200 and up 170 pixels    
  
// *** Find elements below   
 
// an input textbox  
Element input1 = ActiveBrowser.Find.ById("input1");   
  
// a textarea
Element textArea = ActiveBrowser.Find.ById("textarea1");    
  
// an input radio button
Element inputradio = ActiveBrowser.Find.ById("inputradio");    
  
// an input check box
Element inputcheck = ActiveBrowser.Find.ById("inputcheck");    
  
// an input dropdown
Element selection = ActiveBrowser.Find.ById("selection");    
  
// *** DOM actions below
    
// set the text of the input1 textbox to 'test1'
ActiveBrowser.Actions.SetText(input1, "test1");    
  
// set the text of the textarea1 to 'test2'
ActiveBrowser.Actions.SetText(textArea, "test2");    
  
// set the input radio button to selected
ActiveBrowser.Actions.Check(inputradio, true);    
  
// set the input checkbox to selected
ActiveBrowser.Actions.Check(inputcheck, true);
    
// set the dropdown to item index 4
ActiveBrowser.Actions.SelectDropDown(selection, 4);    
  
// set the dropdown to item with text='one1'
ActiveBrowser.Actions.SelectDropDown(selection, "one1");    
  
// set the dropdown to item with value='test'
ActiveBrowser.Actions.SelectDropDown(selection, "test", true);    
  
// the currently selected text should be the dropdown selection
string textSelected = ActiveBrowser.GetSelectedText();   
Assert.AreEqual("test", textSelected, "Actual test is \"{0}\"", textSelected);
```
```VB
 
ActiveBrowser.NavigateTo("http://www.google.com")
  

ActiveBrowser.NavigateTo("~/videosearch")
    

Dim pageTitle As String = ActiveBrowser.PageTitle
Assert.AreEqual("Video Search Page", pageTitle, "Actual page title = ""{0}""", pageTitle)
  

ActiveBrowser.GoBack()
Assert.IsTrue(ActiveBrowser.Url.Contains("Browser.htm"))    
  

ActiveBrowser.GoForward()   
Assert.IsTrue(ActiveBrowser.Url.Contains("google.com"))
  
 
ActiveBrowser.Refresh()
Assert.IsTrue(ActiveBrowser.Url.Contains("google.com"))
  

Dim input1 As Element = ActiveBrowser.Find.ById("input1")
Assert.IsTrue((input1.ElementType = ElementType.Input))   
  

Dim textArea As Element = ActiveBrowser.Find.ById("textarea1")
Assert.IsTrue((textArea.ElementType = ElementType.TextArea))   
  

Dim inputradio As Element = ActiveBrowser.Find.ById("inputradio")
Assert.IsTrue((inputradio.ElementType = ElementType.Input))
   

Dim inputcheck As Element = ActiveBrowser.Find.ById("inputcheck")
Assert.IsTrue((inputcheck.ElementType = ElementType.Input))   
  

Dim selection As Element = ActiveBrowser.Find.ById("selection")
Assert.IsTrue((selection.ElementType = ElementType.Select))  
  

Dim mainTable As Element = Find.ById("mainTable1")
Assert.IsTrue((mainTable.ElementType = ElementType.Table))
  

  

Actions.SetText(Find.Elements("MyTextBox"), "This is a TEST for TextBox!")   
  

Actions.SetText(Find.Elements("MyTextArea"), "This is a TEST for TextArea!")  
  

Actions.Check(checkBox, True)
  

Actions.Check(radio, False)
    

Actions.SelectDropDown(selection, "2", True)  
  

Actions.SelectDropDown(selection, "One")
  

Actions.SelectDropDown(selection, 2)
    

Dim textSelected As String = ActiveBrowser.GetSelectedText()
Assert.AreEqual("test", textSelected, "Actual test is ""{0}""", textSelected)
```

Let's look at some pure UI automation to simulate some of the DOM actions above. Before we look at the sample code, there are few things to note regarding pure UI automation using Telerik Testing Framework:

* When using pure UI actions, you need to make sure that an element is actually visible within the browser client area. In large pages, the browser needs to scroll to make the element visible. Telerik Testing Framework provides a 'ScrollToVisible' action that you should invoke if your page is large and you are not sure if a specific element is visible. This feature is also available out of coded solution in <a href="/features/recorder/overview" target="_blank">the elements menu</a> while recording.

* The 'Desktop' object exposes 'Mouse' & 'Keyboard' objects to represent mouse input vs. keyboard input. Mouse actions usually take a coordinate on the screen to target. Each element in the DomTree has a GetRectangle() method that will retrieve the current X/Y & height/width of an element as it is currently rendered on the screen taking into account any browser scrolling. You can use these rectangle coordinates by passing them in to the mouse action methods.

* Given that pure UI automation simply uses mouse and/or keyboard events, you can use these actions not only to automate elements within a browser, but also to automate simple Win32 windows. The Native Win32 Window Support topic covers this in more detail.
 
The code below shows how to set the text for the 'input1' text box using pure UI automation:

```C#
ActiveBrowser.Actions.ScrollToVisible(input1);

//The ScrollToVisible method could set an element to the top  or the bottom of the page 

input1.ScrollToVisible(ArtOfTest.WebAii.Core.ScrollToVisibleType.ElementBottomAtWindowBottom);
input1.ScrollToVisible(ArtOfTest.WebAii.Core.ScrollToVisibleType.ElementTopAtWindowTop);

Manager.Desktop.Mouse.Click(MouseClickType.LeftClick, input1.GetRectangle());
Manager.Desktop.KeyBoard.TypeText("Hello there", 100);
```
```VB
ActiveBrowser.Actions.ScrollToVisible(input1)
Manager.Desktop.Mouse.Click(MouseClickType.LeftClick, input1.GetRectangle())
Manager.Desktop.KeyBoard.TypeText("Hello there", 100)
```

##Advanced Scenarios##

The 'Mouse' object offers a rich set of APIs to perform some complex UI automation including operations like DragAndDrop that is extremely difficult to perform using direct DOM automation. Such types of operations are becoming more popular with the rich content applications that are emerging on the internet. For example, you can use this DragAndDrop support to automate portals that include web part regions that can be dragged and repositioned like Microsoft's SharePoint server or Google's customized homepage.
 
In addition to that, the 'Mouse' object supports offset coordinates which are very helpful in automating drag/drop actions. For example, if you are attempting to drag a window from one location to another, you need to click-drag its title bar to a destination X/Y coordinate. You can easily choose which part of the window to click-drag using the simplified coordinate offset. This feature is also very suitable for automating image maps.
 
For example, if you are attempting to click the red (x) on this window to drag it to another location:

![Coordinate offset][1]

You would write something like this:

```C#
// get the window element we are trying to drag.
Element mywindow = ActiveBrowser.Find.ByName("mydraggablewindow");
  
// get the destination location.
Element mydestination = ActiveBrowser.Find.ById("mydestinationlocation");
  
// do a drag and drop by grabbing the window from its title (the red x) (offset 2 pixels
// from the top center edge) and dragging it to the center of the destination location.
Manager.Desktop.Mouse.DragDrop(mywindow.GetRectangle(), new System.Drawing.Point(0, 2), OffsetReference.TopCenter,
    mydestination.GetRectangle(), new System.Drawing.Point(0, 0), OffsetReference.AbsoluteCenter);
```
```VB
' get the window element we are trying to drag.
Dim mywindow As Element = ActiveBrowser.Find.ByName("mydraggablewindow")
  
' get the destination location.
Dim mydestination As Element = ActiveBrowser.Find.ById("mydestinationlocation")
  
' do a drag and drop by grabbing the window from its title (the red x) (offset 2 pixels
' from the top center edge) and dragging it to the center of the destination location.
Manager.Desktop.Mouse.DragDrop(mywindow.GetRectangle(), New Drawing.Point(0, 2), OffsetReference.TopCenter, _
    mydestination.GetRectangle(), New Drawing.Point(0, 0), OffsetReference.AbsoluteCenter)
```

[1]: /img/testing-framework/automate-browser-actions/fig1.jpg