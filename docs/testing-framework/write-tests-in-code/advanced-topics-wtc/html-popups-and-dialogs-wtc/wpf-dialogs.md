---
title: WPF Dialogs
page_title: WPF Dialogs
description: "Test Studio WPF dialog handlers in code. SaveFile SaveAs dialog handler in WPF. OpenFile dialog handler in WPF. "
position: 2
---
# WPF Dialog Handlers in Code

The dialogs to store a file locally or open a file in the WPF application also has dedicated handlers in the Testing Framework and need to be defined correctly, before a test can handle these.

## OpenFile Dialog Handler

With OpenFile dialog you need to pass in the full path to the file to open in the WPF application and how the dialog should be handled. The options for OpenFile dialog are: DialogButton.OPEN, DialogButton.CANCEL or DialogButton.CLOSE.

```C#
// Add OpenFile dialog
ArtOfTest.WebAii.Win32.Dialogs.OpenFileDialog.CreateOpenFileDialog wpfOpenDialog = ArtOfTest.WebAii.Win32.Dialogs.OpenFileDialog.CreateOpenFileDialog(ActiveApplication, DialogButton.OPEN, @"d:\name");

// Add the dialog to the DialogMonitor
Manager.DialogMonitor.AddDialog(wpfOpenDialog);

// Start the DialogMonitor
Manager.DialogMonitor.Start();

// Trigger action to show dialog
// Add your code here

// Handle OpenFile dialog
wpfOpenDialog.WaitUntilHandled(15000);

// Clear DialogMonitor from this dialog
Manager.DialogMonitor.RemoveDialog(wpfOpenDialog);
  
// Dialog should be automatically handled
```

## SaveAs Dialog Handler

With SaveAs dialog, you need to pass in the full path and name for the file to save and how the dialog should be handled. The options for SaveAs dialog are: DialogButton.SAVE, DialogButton.CANCEL or DialogButton.CLOSE.

```C#
// Add SaveAs dialog
ArtOfTest.WebAii.Win32.Dialogs.SaveAsDialog.CreateSaveAsDialog wpfSaveAsDialog = ArtOfTest.WebAii.Win32.Dialogs.SaveAsDialog.CreateSaveAsDialog(ActiveApplication, DialogButton.SAVE, @"d:\name");

// Add the dialog to the DialogMonitor
Manager.DialogMonitor.AddDialog(wpfSaveAsDialog);

// Start the DialogMonitor
Manager.DialogMonitor.Start();

// Trigger action to show dialog
// Add your code here

// Handle OpenFile dialog
wpfOpenDialog.WaitUntilHandled(15000);

// Clear DialogMonitor from this dialog
Manager.DialogMonitor.RemoveDialog(wpfSaveAsDialog);
  
// Dialog should be automatically handled

```

> **Note!** To compile the above code include the following using:
>
> using ArtOfTest.WebAii.Win32.Dialogs;

