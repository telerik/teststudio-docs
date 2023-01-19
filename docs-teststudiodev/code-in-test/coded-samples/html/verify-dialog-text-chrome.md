---
title: Verify Dialog Text In Chrome
page_title: Verify Dialog Text In Chrome - Test Studio Dev Documentation
description: Verify Dialog Text In Chrome
position: 1
---
#How to Verify Dialog Text (Chrome)#

*I would like to verify the text of a <a href="/features/recorder/specific-recording-scenario/dialogs" target="_blank">Dialog</a> that is fired from the browser during test execution.*

##Solution##

This could be achieved in a coded solution. The code will both handle the dialog and verify the text within it. What is used to handle this in Chrome is **<a href="https://msdn.microsoft.com/en-us/library/system.windows.automation.automationelement(v=vs.110).aspx" target="_blank">AutomationElement Class</a>**.  A new AutomationElement object is retrieved for the dialog window referenced by the specified window handle and its node is located. The location of the text may vary depending on the machine used for execution though this is handled in the if..else statement.

**Note:** This code requires an assembly reference to the following dlls:

- Telerik.TestStudio.Core.dll 
- UIAutomationClient.dll 
- UIAutomationTypes.dll 
- System.Windows.Forms.dll

The last three could be usually found in *'C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.5\'*.

#### __[C#]__

    {{region }}

    [CodedStep(@"New Coded Step")]
            public void WebTest_CodedStep()
            {
                System.Threading.Thread.Sleep(1000);
                
                AutomationElement dialogElement = AutomationElement.FromHandle(this.ActiveBrowser.Window.Handle);

                AutomationElement chromeNode = dialogElement.GetControlFirstChild(el => el.Current.Name == "Google Chrome");

                if (chromeNode.GetControlNextSibling(el => el.Current.ControlType == ControlType.Custom) != null)
                {
                    // for a VM machine
                    dialogElement = chromeNode.GetControlNextSibling(el => el.Current.ControlType == ControlType.Custom);
                }
                else
                {
                    // for a regular machines
                    dialogElement = dialogElement.GetControlFirstChild(el => el.Current.ControlType == ControlType.Pane);
                }
        
                dialogElement = dialogElement.GetControlLastChild().GetControlLastChild();
                dialogElement = dialogElement.GetControlFirstChild().GetControlFirstChild().GetControlFirstChild().GetControlFirstChild().GetControlFirstChild();

                // Log dialog's text
                Log.WriteLine(dialogElement.Current.Name);

                // handle the dialog
                Manager.Desktop.KeyBoard.KeyPress(Keys.Enter);
            }
    {{endregion}}

#### __[VB]__

    {{region }}
    
    <CodedStep("New Coded Step")> _
    Public Sub WebTest_CodedStep()
        System.Threading.Thread.Sleep(1000)

        Dim dialogElement As AutomationElement = AutomationElement.FromHandle(Me.ActiveBrowser.Window.Handle)

        Dim chromeNode As AutomationElement = dialogElement.GetControlFirstChild(Function(el) el.Current.Name = "Google Chrome")

        If chromeNode.GetControlNextSibling(Function(el) el.Current.ControlType = ControlType.[Custom]) IsNot Nothing Then
            ' for a VM machine
            dialogElement = chromeNode.GetControlNextSibling(Function(el) el.Current.ControlType = ControlType.[Custom])
        Else
            ' for a regular machines
            dialogElement = dialogElement.GetControlFirstChild(Function(el) el.Current.ControlType = ControlType.Pane)
        End If

        dialogElement = dialogElement.GetControlLastChild().GetControlLastChild()
        dialogElement = dialogElement.GetControlFirstChild().GetControlFirstChild().GetControlFirstChild().GetControlFirstChild().GetControlFirstChild()

        ' Log dialog's text
        Log.WriteLine(dialogElement.Current.Name)

        ' handle the dialog
        Manager.Desktop.KeyBoard.KeyPress(Keys.Enter)
    End Sub
    {{endregion}}

Ensure you add the following *using or Imports* statements to the top of the code-behind file:

#### __[C#]__

    {{region }}

    using System.Windows.Automation;
    using ArtOfTest.Common.Extensions;
    using System.Windows.Forms;
    {{endregion}}

#### __[VB]__

    {{region }}

    Imports System.Windows.Automation
    Imports ArtOfTest.Common.Extensions
    Imports System.Windows.Forms
    {{endregion}}
