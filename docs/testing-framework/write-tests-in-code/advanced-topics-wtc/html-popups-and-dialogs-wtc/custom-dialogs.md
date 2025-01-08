---
title: Handle Custom Dialogs
page_title: Handle Custom Dialogs
description: "Test Studio Testing Framework Custom Dialog handling. Handle a dialog in custom manner in a coded step in Test Studio. Coded test to handle dialogs in Test Studio using custom logic."
position: 10
---
# Custom Dialog Handler

If for whatever reason you decide that you don't like the way the dialog is being handled or want to perform extra tasks before handling the dialog, you can simply craft your own dialog handling code and then ask the dialog to call your code instead of its dialog handling code. Here is an example:

```C#
public void DoCustomDialogHandlingForBuiltInDialogs()
 {
    AlertDialog myAlertDialog = new AlertDialog(ActiveBrowser, DialogButton.OK);
    myAlertDialog.HandlerDelegate = new DialogHandlerDelegate(MyCustomAlertHandler);
  
    // Add dialog to monitor and start monitoring
    Manager.DialogMonitor.AddDialog(myAlertDialog);
    Manager.DialogMonitor.Start();
  
    Actions.InvokeScript("InvokeAlert()");
  
 }
  
///<summary>
/// Custom dialog handler delegate
///</summary>
///<param name="dialog">The dialog to handle</param>
///<returns></returns>
public bool MyCustomAlertHandler(IDialog dialog)
{
    // Simply close the dialog
    dialog.Window.Close();
  
    try
    {
         // Wait until it is closed
         dialog.Window.WaitForVisibility(false, 50);
         Log.WriteLine("Alert Handled!");
         return true;
    }
    catch
    {
         Log.WriteLine("Failed to handle alert!");
         // return false if the dialog did not close as expected
         return false;
    }
}
```
```VB
<TestMethod()> _
Public Sub DoCustomDialogHandlingForBuiltInDialogs()
  
    Dim myAlertDialog As AlertDialog = New AlertDialog(ActiveBrowser, DialogButton.OK)
    myAlertDialog.HandlerDelegate = New DialogHandlerDelegate(AddressOf MyCustomAlertHandler)
    ' Add dialog to monitor and start monitoring
    Manager.DialogMonitor.AddDialog(myAlertDialog)
    Manager.DialogMonitor.Start()
    Actions.InvokeScript("InvokeAlert()")
  
End Sub
  
''' <summary>
''' Custom dialog handler delegate
''' </summary>
''' <param name="dialog">The dialog to handle</param>
Public Sub MyCustomAlertHandler(ByVal dialog As ArtOfTest.WebAii.Win32.Dialogs.IDialog)
  
    ' Simply close the dialog
    dialog.Window.Close()
    Try
        ' Wait until it is closed
        dialog.Window.WaitForVisibility(False, 50)
        Log.WriteLine("Alert Handled!")
        Return
    Catch ex As System.Exception
        Log.WriteLine("Failed to handle alert!")
        ' return false if the dialog did not close as expected
        Return
    End Try
  
End Sub
```


> **To compile the above code include the following using:**
>
> using ArtOfTest.WebAii.Win32.Dialogs;
