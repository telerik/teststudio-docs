---
title: Verify Dialog Text In Chrome
page_title: Verify Dialog Text In Chrome
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#How to Verify Dialog Text (Chrome)#

*I would like to verify the text of a <a href="/features/dialogs-and-popups/Dialogs" target="_blank">Dialog</a> that is fired from the browser during test execution.*

##Solution##

This could be achieved in a coded solution. The code will both handle the dialog and verify the text within it. What is used to handle this in Chrome is **<a href="https://msdn.microsoft.com/en-us/library/system.windows.automation.automationelement(v=vs.110).aspx" target="_blank">AutomationElement Class</a>**.  A new AutomationElement object is retrieved for the dialog window referenced by the specified window handle and its node is located. The location of the text may vary depending on the machine used for execution though this is handled in the if..else statement. 


**Note:** This code requires an assembly reference to  

- Telerik.TestStudio.Core.dll 
- UIAutomationClieant.dll 
- UIAutomationTypes.dll 
- System.Windows.Forms.dll

The last three could be usually found in *'C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.5\'*. 

<a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Here</a> is an article on how to add an assembly reference in the Standalone version.

```C# 
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
```
```VB 
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
```


Ensure you add the following *using or Imports* statements to the top of the code-behind file.Scroll to the top of the code file and add these lines:


```C#
using System.Windows.Automation;
using ArtOfTest.Common.Extensions;
using System.Windows.Forms;
```
```VB
Imports System.Windows.Automation
Imports ArtOfTest.Common.Extensions
Imports System.Windows.Forms
```

