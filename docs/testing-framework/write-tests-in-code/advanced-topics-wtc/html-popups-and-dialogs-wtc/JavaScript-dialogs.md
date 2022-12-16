---
title: Alert Dialogs
page_title: Alert Dialogs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#Handling Alert Dialogs#

With Alerts, you only need to define how the alert should be handled. Your options for alert handling are: DialogButton.OK or DialogButton.CLOSE. Confirm and Prompt dialogs have the same structure and the Testing Framework uses the same built-in handler. 

```C#
// Define the Alert dialog

ArtOfTest.WebAii.Win32.Dialogs.AlertDialog alertDlg = new ArtOfTest.WebAii.Win32.Dialogs.AlertDialog(Activebrowser, DialogButton.OK); 

// Add the defined alert dialog to the DialogMonitor 
Manager.DialogMonitor.AddDialog(alertDlg));

// Start the DialogMonitor
Manager.DialogMonitor.Start();

// At this point when the dialog definition is added to the DialogMonitor 
// and it is started you can insert the action, 
// which triggers the alert/confirm/prompt dialog 

// The current example uses JavaScript call to invoke an alert dialog. 
// But you can use any sort of action which triggers the dialog in the tested page -
// including click on element or type some text.
Actions.InvokeScript("InvokeAlert()");

// The dialog gets automatically handled once it appears. 

// Then you need to remove the handled dialog from the DialogMonitor and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(alertDlg);
Manager.DialogMonitor.Stop();


```
```VB
' Define the Alert dialog

ArtOfTest.WebAii.Win32.Dialogs.AlertDialog alertDlg = New ArtOfTest.WebAii.Win32.Dialogs.AlertDialog(Activebrowser, DialogButton.OK)

' Add the defined alert dialog to the DialogMonitor 
Manager.DialogMonitor.AddDialog(alertDlg)

' Start the DialogMonitor
Manager.DialogMonitor.Start()

' At this point when the dialog definition is added to the DialogMonitor 
' and it is started you can insert the action, 
' which triggers the alert/confirm/prompt dialog 

' The current example uses JavaScript call to invoke an alert dialog. 
' But you can use any sort of action which triggers the dialog in the tested page -
' including click on element or type some text.
Actions.InvokeScript("InvokeAlert()")

' The dialog gets automatically handled once it appears. 

' Then you need to remove the handled dialog from the DialogMonitor and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(alertDlg)
Manager.DialogMonitor.Stop()

```


> **To compile the above code include the following using:**
>
> using ArtOfTest.WebAii.Win32.Dialogs;
