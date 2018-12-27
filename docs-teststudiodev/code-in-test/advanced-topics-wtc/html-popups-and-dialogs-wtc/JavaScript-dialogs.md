---
title: Alert Dialogs
page_title: Alert Dialogs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#Handling Alert Dialogs#

With Alerts, you only need to define how the alert should be handled. Your options for alert handling are: DialogButton.OK or DialogButton.CLOSE.

```C#
// Add an alert dialog to monitor
Manager.DialogMonitor.AddDialog(new AlertDialog(ActiveBrowser, DialogButton.OK));

// Given that there were not dialog attribute set, the manager will not start the monitoring.
// You need to invoke the monitoring
Manager.DialogMonitor.Start();

// Invoke an alert dialog
Actions.InvokeScript("InvokeAlert()");

// The dialog will now be automatically handled transparently in the background without any help from the test code.
```

 ```VB
' Add an alert dialog to monitor
Manager.DialogMonitor.AddDialog(New AlertDialog(ActiveBrowser, DialogButton.OK))

' Given that there were not dialog attribute set, the manager will not start the monitoring.
' You need to invoke the monitoring
Manager.DialogMonitor.Start()

' Invoke an alert dialog
Actions.InvokeScript("InvokeAlert()")

' The dialog will now be automatically handled transparently in the background without any help from the test code.
```
> **To compile the above code include the following using:**
>
> using ArtOfTest.WebAii.Win32.Dialogs;
