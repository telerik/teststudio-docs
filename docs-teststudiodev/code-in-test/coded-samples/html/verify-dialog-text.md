---
title: Verify Dialog Text
page_title: Verify Dialog Text - Test Studio Dev Documentation
description: Verify Dialog Text
position: 1
---
# How to Verify Dialog Text (Internet Explorer only) #

*I would like to verify the text of a <a href="/features/recorder/specific-recording-scenario/dialogs" target="_blank">Dialog</a> that is fired from the browser during test execution.*

## Solution ##

This is possible with a coded solution.  The code will both handle the dialog and verify the text within it. The second part uses a <a href="http://msdn.microsoft.com/en-us/library/ms173171(v=vs.80).aspx" target="_blank">delegate</a> to implement a custom handler for the dialog.

#### __[C#]__

    {{region }}

    string dialogText;
    
    [CodedStep(@"Navigate then verify text in popup dialog")]
    public void VerifyDialogText_CodedStep()
    {
        ActiveBrowser.NavigateTo("http://www.w3schools.com/JS/tryit.asp?filename=tryjs_alert");
    
        // Click the button to fire the Alert Dialog inside the browser
        FrameInfo myFrame = new FrameInfo("iframeResult", "", "", 0);
        Browser frame = ActiveBrowser.Frames[myFrame];
        HtmlButton tryItButton = frame.Find.ByTagIndex<HtmlButton>("button", 0);
        Assert.IsNotNull(tryItButton);
        
        
        // Initialize custom 'Alert' dialog handler
        AlertDialog alertDialog = AlertDialog.CreateAlertDialog(ActiveBrowser, DialogButton.OK);
        Manager.DialogMonitor.Start();
        alertDialog.HandlerDelegate = MyCustomAlertHandler;
        Manager.DialogMonitor.AddDialog(alertDialog);
        tryItButton.Click();
        
        // Wait Until Dialog is Handled.
        alertDialog.WaitUntilHandled(20000);

        // Validate the text that was captured by the custom dialog handler
        Assert.AreEqual<string>("I am an alert box!", dialogText);
    }
    
    public void MyCustomAlertHandler(IDialog dialog)
    {
        // Capture the text displayed in the dialog. The contents will be validated by the main thread.
        dialogText = dialog.Window.AllChildren[dialog.Window.AllChildren.Count - 1].Caption;
        Log.WriteLine("Dialog text: " + dialogText);
    
        Manager.Desktop.KeyBoard.KeyPress(Keys.Enter);
        dialog.HandleCount++;
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Private dialogText As String
    
    <CodedStep("Navigate then verify text in popup dialog")> _
    Public Sub VerifyDialogText_CodedStep()
        ActiveBrowser.NavigateTo("http://www.w3schools.com/JS/tryit.asp?filename=tryjs_alert")
    
        
        Dim alertDialog__1 As AlertDialog = AlertDialog.CreateAlertDialog(ActiveBrowser, DialogButton.OK)
        alertDialog__1.HandlerDelegate = AddressOf MyCustomAlertHandler
        Manager.DialogMonitor.AddDialog(alertDialog__1)
    
        
        Dim tryItButton As HtmlButton = ActiveBrowser.Frames("view").Find.ByTagIndex(Of HtmlButton)("button", 0)
        Assert.IsNotNull(tryItButton)
        tryItButton.Click()
    
        
        alertDialog__1.WaitUntilHandled(5000)
    
        
        Assert.AreEqual(Of String)("I am an alert box!", dialogText)
    End Sub
    
    Public Sub MyCustomAlertHandler(dialog As IDialog)
        
        dialogText = dialog.Window.AllChildren(dialog.Window.AllChildren.Count - 1).Caption
        Log.WriteLine(Convert.ToString("Dialog text: ") & dialogText)
    
        Manager.Desktop.KeyBoard.KeyPress(Keys.Enter)
        dialog.HandleCount += 1
    End Sub
    {{endregion}}

Ensure you add the following *using* or *Imports* statements to the top of the code-behind file.

#### __[C#]__

    {{region }}

    using ArtOfTest.WebAii.Win32.Dialogs;
    using System.Windows.Forms;
    {{endregion}}

#### __[VB]__

    {{region }}

    Imports ArtOfTest.WebAii.Win32.Dialogs
    Imports System.Windows.Forms
    {{endregion}}
