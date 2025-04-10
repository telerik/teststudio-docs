---
title: Prompt Dialogs
page_title: Prompt Dialogs
description: "Handle Prompt dialog in coded step in Test Studio. Coded test to handle prompt dialogs in Test Studio. Test Studio Testing Framework Prompt Dialog handling. "
position: 4
---
# Handling Prompt Dialogs

__Telerik Testing Framework__ includes native support for dialog handling (under the _ArtOfTest.WebAii.Win32.Dialogs_ namespace) with built-in handlers of the common browser dialogs. The Prompt dialog is one of the covered dialogs with built-in handlers. The below code demonstrates how to implement the handler and use it to handle the dialog.

>__Important!__
><br>
> Reference the _ArtOfTest.WebAii.Win32.Dialogs.dll_ in the project and insert it as _using_ in the code file.
><br>
> _using ArtOfTest.WebAii.Win32.Dialogs;_

````C#
// Define the Prompt dialog and how it needs to be handled - choose between Ok and Cancel
var promptDlg = new ArtOfTest.WebAii.Win32.Dialogs.PromptDialog(Manager.ActiveBrowser, DialogButton.OK, "message to type");

// The dialog monitor is the Testing Framework built-in class for monitoring the dialogs to be handled throughout the test
// Add the defined prompt dialog promptDlg to the DialogMonitor collection and start it 

Manager.DialogMonitor.AddDialog(promptDlg);
Manager.DialogMonitor.Start();

// At this point when the dialog definition is added to the DialogMonitor 
// and it is started you can insert the action, 
// which triggers the prompt dialog 

// This is the action that invokes the dialog for this specific example 
// The next four lines need to be replaced for the specific application under test
ActiveBrowser.Window.SetFocus();
Pages.DialogsTestingPage.PromptButtonTag.ScrollToVisible(ArtOfTest.WebAii.Core.ScrollToVisibleType.ElementCenterAtWindowCenter);
Pages.DialogsTestingPage.PromptButtonTag.MouseClick();

// Here we wait for the dialog to be handled eiether specify or Settings.Current.ClientReadyTimeout will be used by default
// Wait for the dialog to appear and to be handled. The WaitUntilHandled() method accepts miliseconds to define the time to wait. If no value is defined, the Settings.Current.ClientReadyTimeout is in use 
promptDlg.WaitUntilHandled();

// The dialog gets automatically handled once it appears. 

// Remove the handled dialog from the DialogMonitor collection and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(promptDlg);
Manager.DialogMonitor.Stop();

// Optionally, you might need to refresh the DOM used from Test Studio after the dialog was handled
// The code to use for this is on the below line and will be necessary if you experience any issues with the next actions 
// especially if the elements to use are related to the action confirmed with the dialog handling
//Manager.ActiveBrowser.RefreshDomTree();

````
````VB
' Define the Prompt dialog
IDialog promptDlg = New ArtOfTest.WebAii.Win32.Dialogs.PromptDialog(Manager.ActiveBrowser, DialogButton.OK, "stringMsg")

' The dialog monitor is the Testing Framework built-in class for monitoring the dialogs to be handled throughout the test
' Add the defined prompt dialog to the DialogMonitor 
Manager.DialogMonitor.AddDialog(promptDlg)

' Start the DialogMonitor
Manager.DialogMonitor.Start()

' At this point when the dialog definition is added to the DialogMonitor 
' and it is started you can insert the action, 
' which triggers the prompt/prompt/prompt dialog 

' The current example uses JavaScript call to invoke a prompt dialog. 
' But you can use any sort of action which triggers the dialog in the tested page -
' including click on element or type some text.
Actions.InvokeScript("InvokePrompt()")

' Handle the prompt dialog. 
promptDlg.Handle()

' Then you need to remove the handled dialog from the DialogMonitor and stop the monitoring 
Manager.DialogMonitor.RemoveDialog(promptDlg)
Manager.DialogMonitor.Stop()

````
