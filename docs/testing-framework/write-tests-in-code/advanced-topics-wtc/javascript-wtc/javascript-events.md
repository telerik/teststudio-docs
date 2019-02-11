---
title: JavaScript Events
page_title: JavaScript Events
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#JavaScript Events#

##Invoking JavaScript Events##

Telerik Testing Framework allows you to invoke JavaScript events directly with or without event arguments. For example:

```C#
// Invoke the OnFocus event
HtmlButton b = Find.ById<HtmlButton>("b");
b.InvokeEvent(ScriptEventType.OnFocus);
// or
Actions.InvokeEvent(b.BaseElement, ScriptEventType.OnFocus);
 
// To invoke an event with an argument do something like this
HtmlTextArea area1 = Find.ById<HtmlTextArea>("area1");
Element body1 = Find.ById("body1");
 
MouseEvent me = new MouseEvent();
me.Type = "mouseover";
me.SetRelatedTarget(body1);
area1.InvokeEvent(me);
```
```VB
' Invoke the OnFocus event
Dim b As HtmlButton = Find.ById(Of HtmlButton)("b")
b.InvokeEvent(ScriptEventType.OnFocus)
' or
Actions.InvokeEvent(b.BaseElement, ScriptEventType.OnFocus)
 
' To invoke an event with an argument do something like this
Dim area1 As HtmlTextArea = Find.ById(Of HtmlTextArea)("area1")
Dim body1 As Element = Find.ById("body1")
 
Dim [me] As New MouseEvent()
[me].Type = "mouseover"
[me].SetRelatedTarget(body1)
area1.InvokeEvent([me])
```

##JavaScript Event Handlers##

The framework gives you the ability to attach a .NET event handler to your JavaScript happening in the browser. Start by defining your event handler like this:

```C#
private volatile bool _clickHandled;
private System.Threading.AutoResetEvent _clickARE;
 
private void OnClick(object sender, JavascriptEventArgs e)
{
    _clickHandled = true;
    _clickARE.Set();
}
```
```VB
Private _clickHandled As Boolean
_clickHandled
Private _clickARE As System.Threading.AutoResetEvent
 
Private Sub OnClick(ByVal sender As Object, ByVal e As JavascriptEventArgs)
    _clickHandled = True
    _clickARE.[Set]()
End Sub
```

All that's left is to attach the event handler to an element on the DOM like this:

```C#
[TestMethod]
public void ClickHandler()
{
    _clickARE = new System.Threading.AutoResetEvent(false);
    _clickHandled = false;
 
    HtmlButton b = Find.ById<HtmlButton>("b");
 
    // Attach a listener to the click event on the button.
    b.AddEventListener("click", OnClick);
 
    // Invoke the event.
    b.InvokeEvent(ScriptEventType.OnClick);
 
    // Wait until the event is fired.
    _clickARE.WaitOne(500);
 
    Assert.IsTrue(_clickHandled);
}
```
```VB
<TestMethod()> _
Public Sub ClickHandler()
    _clickARE = New System.Threading.AutoResetEvent(False)
    _clickHandled = False
 
    Dim b As HtmlButton = Find.ById(Of HtmlButton)("b")
 
    ' Attach a listener to the click event on the button.
    b.AddEventListener("click", AddressOf OnClick)
 
    ' Invoke the event.
    b.InvokeEvent(ScriptEventType.OnClick)
 
    ' Wait until the event is fired.
    _clickARE.WaitOne(500)
 
    Assert.IsTrue(_clickHandled)
End Sub
```