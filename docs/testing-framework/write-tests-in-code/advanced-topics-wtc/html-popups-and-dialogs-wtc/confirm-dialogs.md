---
title: Confirm Dialogs
page_title: Confirm Dialogs
description: "Test Studio Testing Framework Dialog handling. Handle Confirm dialog in coded step in Test Studio. Coded test to handle confirm dialogs in Test Studio."
position: 2
---
# Handling Confirm Dialogs

__Telerik Testing Framework__ includes native support for dialog handling (under the _ArtOfTest.WebAii.Win32.Dialogs_ namespace) with built-in handlers of the common browser dialogs. The Confirm dialog is one of the covered dialogs with built-in handlers. The below code demonstrates how to implement the handler and use it to handle the dialog. 

```C#
// Define the Confirm dialog
IDialog confirmDlg = new ArtOfTest.WebAii.Win32.Dialogs.ConfirmDialog(Manager.ActiveBrowser, DialogButton.OK); 

// The dialog monitor is the Testing Framework built-in class for monitoring the dialogs to be handled throughout the test
// Add the defined confirm dialog to the DialogMonitor 
Manager.DialogMonitor.AddDialog(confirmDlg);

// Start the DialogMonitor 
Manager.DialogMonitor.Start();

// At this point when the dialog definition is added to the DialogMonitor 
// and it is started you can insert the action, 
// which triggers the confirm/confirm/prompt dialog 

// The current example uses JavaScript call to invoke a confirm dialog. 
// But you can use any sort of action which triggers the dialog in the tested page -
// including click on element or type some text.
Actions.InvokeScript("InvokeConfirm()");

// The dialog gets automatically handled once it appears. 

// Then you need to remove the handled dialog from the DialogMonitor and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(confirmDlg);
Manager.DialogMonitor.Stop();
```
```VB
' Define the Confirm dialog
IDialog confirmDlg = New ArtOfTest.WebAii.Win32.Dialogs.ConfirmDialog(Manager.ActiveBrowser, DialogButton.OK)

' The dialog monitor is the Testing Framework built-in class for monitoring the dialogs to be handled throughout the test
' Add the defined confirm dialog to the DialogMonitor 
Manager.DialogMonitor.AddDialog(confirmDlg)

' Start the DialogMonitor
Manager.DialogMonitor.Start()

' At this point when the dialog definition is added to the DialogMonitor 
' and it is started you can insert the action, 
' which triggers the confirm/confirm/prompt dialog 

' The current example uses JavaScript call to invoke a confirm dialog. 
' But you can use any sort of action which triggers the dialog in the tested page -
' including click on element or type some text.
Actions.InvokeScript("InvokeConfirm()")

' The dialog gets automatically handled once it appears. 

' Then you need to remove the handled dialog from the DialogMonitor and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(confirmDlg)
Manager.DialogMonitor.Stop()

```


>__Important!__
>To compile the above code include the following using in the coded file: 
><br>
>using ArtOfTest.WebAii.Win32.Dialogs;
