---
title: Logon Dialogs
page_title: Logon Dialogs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#Logon Dialogs#

With Logon dialogs, you need to pass in the username/password that you want used and how the dialog should be handled. Your options for the Logon dialog are: DialogButton.OK, DialogButton.CANCEL or DialogButton.CLOSE.

```C#
// Add a logon dialog support with username/password
Manager.DialogMonitor.AddDialog(new LogonDialog(ActiveBrowser, "<username>", "<password>", DialogButton.OK));
Manager.DialogMonitor.Start();

// Navigate to a page that need a logon
ActiveBrowser.NavigateTo("<Place a Url to LogOn to here>");

// Dialog should be automatically handled
```
```VB
' Add a logon dialog support with username/password
Manager.DialogMonitor.AddDialog(New LogonDialog(ActiveBrowser, "<username>", "<password>", DialogButton.OK))
Manager.DialogMonitor.Start()

' Navigate to a page that need a logon
ActiveBrowser.NavigateTo("<Place a Url to LogOn to here>")

' Dialog should be automatically handled
```


> **To compile the above code include the following using:**
>
> using ArtOfTest.WebAii.Win32.Dialogs;
