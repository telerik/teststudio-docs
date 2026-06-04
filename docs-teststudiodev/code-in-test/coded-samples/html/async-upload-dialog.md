---
title: AsyncUpload Dialog
page_title: AsyncUpload Dialog - Test Studio Dev Documentation
description: AsyncUpload Dialog
position: 1
---
# How to Handle the AsyncUpload Dialog

There are differences in how RadAsyncUpload is interpreted across different browsers. AsyncUpload is built over Silverlight in Internet Explorer, but rendered in HTML5 in the other browsers (Firefox, Safari, and Chrome). This greatly affects cross-browser UI Automation. You can work around the problem by using a coded step to handle the dialog:

````C#
    public void Upload(int index, string filePath)
    {
    FileUploadDialog uploadDialog = new FileUploadDialog(OwnerBrowser, filePath, DialogButton.OPEN, this.UploadDialogTitle);
    Manager.Current.DialogMonitor.AddDialog(uploadDialog);
    Manager.Current.DialogMonitor.Start();
    this.FileSelect(index);
    OwnerBrowser.WaitUntilReady();
    uploadDialog.WaitUntilHandled();
    Manager.Current.DialogMonitor.Stop();
    Manager.Current.DialogMonitor.RemoveDialog(uploadDialog);
    }
````
````VB
    Public Sub Upload(index As Integer, filePath As String)
        Dim uploadDialog As New FileUploadDialog(OwnerBrowser, filePath, DialogButton.OPEN, Me.UploadDialogTitle)
        Manager.Current.DialogMonitor.AddDialog(uploadDialog)
        Manager.Current.DialogMonitor.Start()
        Me.FileSelect(index) 
        OwnerBrowser.WaitUntilReady()
        uploadDialog.WaitUntilHandled()
        Manager.Current.DialogMonitor.[Stop]()
        Manager.Current.DialogMonitor.RemoveDialog(uploadDialog)
    End Sub
````


