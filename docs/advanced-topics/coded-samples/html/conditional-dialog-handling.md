---
title: Conditional Dialog Handling
page_title: Conditional Dialog Handling
description: "Learn how to conditionally handle dialogs in Test Studio using C# and VB.NET. This guide provides a coded solution to manage dialogs dynamically during automated testing, ensuring seamless test execution."
position: 1
---
# Conditionally Handling Dialog

***I would like to conditionally handle a dialog. If it appears, I'd like to handle it normally. If it doesn't, I'd like to continue with test execution.***

## Solution

This is possible with a coded solution. The action that potentially triggers the dialog must be included in the code.

 __Tip!__
><br>
><br>
> The example shows handling an alert dialog in a web test. Though the sample can be adjusted to implement any of the <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/built-in-handlers" target="_blank">available built-in dialog handlers</a> including WPF dialogs. 

```C#
ActiveBrowser.NavigateTo("http://www.w3schools.com/js/tryit.asp?filename=tryjs_alert");
 
//Create the dialog and add it to the monitor
AlertDialog ad = AlertDialog.CreateAlertDialog(ActiveBrowser, DialogButton.OK);
Manager.DialogMonitor.AddDialog(ad);
 
//Trigger the dialog
//Comment out the following line to see the code work when the dialog isn't fired
Manager.ActiveBrowser.Frames["iframeResult"].Find.ByContent<HtmlButton>("Try it").Click();
 
//If the dialog fires, it's handled
//If not, the exception is silently disposed
try
{
    ad.WaitUntilHandled(2000);
}
catch (TimeoutException)
{
}
 
//Remove the dialog from the monitor
Manager.DialogMonitor.RemoveDialog(ad);
 
ActiveBrowser.NavigateTo("http://www.bing.com");
```
```VB
ActiveBrowser.NavigateTo("http://www.w3schools.com/js/tryit.asp?filename=tryjs_alert")
 

Dim ad As AlertDialog = AlertDialog.CreateAlertDialog(ActiveBrowser, DialogButton.OK)
Manager.DialogMonitor.AddDialog(ad)
 

Manager.ActiveBrowser.Frames("iframeResult").Find.ByContent(Of HtmlButton)("Try it").Click()
 

Try
    ad.WaitUntilHandled(2000)
Catch generatedExceptionName As TimeoutException
End Try
 

Manager.DialogMonitor.RemoveDialog(ad)
 
ActiveBrowser.NavigateTo("http://www.bing.com")
```

