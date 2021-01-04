---
title: Log Error Dialogs
page_title: Log Error Dialogs | Test Studio Dev Documentation
description: Log Error Dialogs
position: 1
---
#Log Error Dialogs#

*My application can potentially display a dialog containing an error message during test execution. The dialog can appear multiple times and will not always appear at the same point in the test, therefore I cannot use a standard Dialog Handler step.
 
I want to capture these error messages and automatically handle these dialogs if they appear.*

##Solution##

This is possible with a coded solution. The stipulation is that the dialog is displayed the same way and has the same title in each browser:

![Dialog][1]

1.Add an Assembly Reference to *System.Windows.Forms*.
2.Add a <a href="/code-in-test/features-in-code#Coded-Step" target="_blank">coded step</a> to the beginning of the test that creates a dialog monitor.
3.Define a custom dialog handler that is referenced in the coded step.
4.Override the *OnAfterTestCompleted* method to log whatever text the dialog handler captured.
5.Auto reset the dialog handler in case of multiple dialogs.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the Dynamic Pages Reference region:

#### __[C#]__

    {{region }}

    using System.Threading;
    using System.Windows.Forms;
    using ArtOfTest.WebAii.Win32.Dialogs;
    
    namespace TestProject7
    {
        public class HandleDialogLogText : BaseWebAiiTest
        { 
            string txt = string.Empty;
            GenericDialog errorDialog;
            
            public override void OnAfterTestCompleted(TestResult result)
            {
                Log.WriteLine("OnAfterTestCompleted dialog text: " + txt);
                base.OnAfterTestCompleted(result);
            }
        
            [CodedStep(@"New Coded Step")]
            public void HandleDialogLogText_CodedStep()
            {
                errorDialog = new GenericDialog(ActiveBrowser, "Custom Title", true);
                errorDialog.HandlerDelegate = HandleErrorDialog;
                Manager.DialogMonitor.AddDialog(errorDialog);          
            }
            
            public void HandleErrorDialog(IDialog dialog)
            {
                txt += "\r\n";
                txt += "Dialog " + (dialog.HandleCount + 1).ToString() + ": " + dialog.Window.AllChildren[dialog.Window.AllChildren.Count - 1].Caption;
                Manager.Desktop.KeyBoard.KeyPress(Keys.Enter);
                dialog.HandleCount++;
                Thread resetDialog = new Thread(new ThreadStart(ResetDialog));
                resetDialog.Start();
            }
            
            public void ResetDialog()
            {
                Thread.Sleep(500);
                errorDialog.CurrentState = DialogCurrentState.NotActive;
            }
        }
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Imports System.Threading
    Imports System.Windows.Forms
    Imports ArtOfTest.WebAii.Win32.Dialogs
    
    Namespace TestProject7
        Public Class HandleDialogLogText
            Inherits BaseWebAiiTest
            Private txt As String = String.Empty
            Private errorDialog As GenericDialog
    
            Public Overrides Sub OnAfterTestCompleted(result As TestResult)
                Log.WriteLine("OnAfterTestCompleted dialog text: " + txt)
                MyBase.OnAfterTestCompleted(result)
            End Sub
    
            <CodedStep("New Coded Step")> _
            Public Sub HandleDialogLogText_CodedStep()
                errorDialog = New GenericDialog(ActiveBrowser, "Custom Title", True)
                errorDialog.HandlerDelegate = HandleErrorDialog
                Manager.DialogMonitor.AddDialog(errorDialog)
            End Sub
    
            Public Sub HandleErrorDialog(dialog As IDialog)
                txt += vbCr & vbLf
                txt += "Dialog " + (dialog.HandleCount + 1).ToString() + ": " + dialog.Window.AllChildren(dialog.Window.AllChildren.Count - 1).Caption
                Manager.Desktop.KeyBoard.KeyPress(Keys.Enter)
                dialog.HandleCount += 1
                Dim resetDialog__1 As New Thread(New ThreadStart(ResetDialog))
                resetDialog__1.Start()
            End Sub
    
            Public Sub ResetDialog()
                Thread.Sleep(500)
                errorDialog.CurrentState = DialogCurrentState.NotActive
            End Sub
        End Class
    End Namespace
    {{endregion}}

[1]: images/log-error-dialogs/fig1.png