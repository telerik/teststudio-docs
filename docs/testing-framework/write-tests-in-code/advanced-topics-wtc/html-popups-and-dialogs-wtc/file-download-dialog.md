---
title: FileDownload Dialog
page_title: FileDownload Dialog
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/write-tests-in-code/advanced-topics/handling-html-popups-and-dialogs/built-in-dialog-handlers/handling-filedownload-dialog.aspx, /user-guide/write-tests-in-code/advanced-topics/handling-html-popups-and-dialogs/built-in-dialog-handlers/handling-filedownload-dialog
position: 2
---
#Handling FileDownload Dialogs#

With FileDownload, you need to pass in the full path to the download location and how the dialog should be handled. 

```C#
DownloadDialogsHandler dialog = new DownloadDialogsHandler (Manager.ActiveBrowser, DialogButton.SAVE, @"D:\text.txt", Manager.Desktop); 
 
Manager.DialogMonitor.Start();
 
//Trigger the dialog.

Element.Click(false); 
 
dialog.WaitUntilHandled(30000);

```
```VB
Dim dialog As New DownloadDialogsHandler(Manager.ActiveBrowser, DialogButton.SAVE, "D:\text.txt", Manager.Desktop)

Manager.DialogMonitor.Start()

'Trigger the dialog.

Element.Click(False)

dialog.WaitUntilHandled(30000)
```


> **To compile the above code include the following using:**
>
> using ArtOfTest.WebAii.Win32.Dialogs;

