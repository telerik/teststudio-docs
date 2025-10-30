---
title: Log Clipboard Text
page_title: Log Clipboard Text
description: "Learn how to log and output clipboard text during Test Studio test execution. Step-by-step code examples show how to access and display clipboard content in automated tests."
position: 1
---
# Log Clipboard Text

*My test copies text into the Clipboard and I would like to log its content.*

## Solution

This is possible with a coded solution:

1.&nbsp; <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2.&nbsp; Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test after the step that populates the Clipboard.
 
Here is the full code-behind file, excluding the standard *using/Imports* statements and the Dynamic Pages Reference region:

```C#
using System.Windows.Forms;
using System.Threading;
 
namespace TestProject8
{     
    public class ClipboardTest : BaseWebAiiTest
    {  
        public string ClipboardMethod()
        {
            string content = Clipboard.GetText();
            return content;
        }
     
        [CodedStep(@"New Coded Step")]
        public void ClipboardTest_CodedStep()
        {
            string content = string.Empty;
             
            var thread = new Thread(obj =>
            {
                content = this.ClipboardMethod();
            });
             
            thread.SetApartmentState(ApartmentState.STA);
            thread.Start();
            thread.Join();
             
            Log.WriteLine(content);
        }
    }
}
```
```VB
Imports System.Windows.Forms
Imports System.Threading
 
Namespace TestProject8
    Public Class ClipboardTest
        Inherits BaseWebAiiTest
        Public Function ClipboardMethod() As String
            Dim content As String = Clipboard.GetText()
            Return content
        End Function
 
        <CodedStep("New Coded Step")> _
        Public Sub ClipboardTest_CodedStep()
            Dim content As String = String.Empty
 
            Dim thread = New Thread(Function(obj) Do
                content = Me.ClipboardMethod()
            End Function)
 
            thread.SetApartmentState(ApartmentState.STA)
            thread.Start()
            thread.Join()
 
            Log.WriteLine(content)
        End Sub
    End Class
End Namespace
```