---
title: Logon Dialogs
page_title: Logon Dialogs
description: "Handle a Logon dialog in a coded step in Test Studio. Coded test to handle Logon dialogs in Test Studio. Test Studio Testing Framework Logon Dialog handling."
position: 5
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
