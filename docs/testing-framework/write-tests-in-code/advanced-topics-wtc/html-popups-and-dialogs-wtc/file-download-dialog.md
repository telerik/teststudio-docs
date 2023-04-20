---
title: FileDownload Dialog
page_title: FileDownload Dialog
description: "Handle a download dialog in a coded step in Test Studio. Coded test to handle download dialogs in Test Studio. Test Studio Testing Framework Download Dialog handling."
previous_url: /user-guide/write-tests-in-code/advanced-topics/handling-html-popups-and-dialogs/built-in-dialog-handlers/handling-filedownload-dialog.aspx, /user-guide/write-tests-in-code/advanced-topics/handling-html-popups-and-dialogs/built-in-dialog-handlers/handling-filedownload-dialog
position: 7
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

