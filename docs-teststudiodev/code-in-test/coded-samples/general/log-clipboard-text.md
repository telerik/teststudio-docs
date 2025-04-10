---
title: Log Clipboard Text
page_title: Log Clipboard Text - Test Studio Dev Documentation
description: Log Clipboard Text
position: 1
---
# Log Clipboard Text

*My test copies text into the Clipboard and I would like to log its content.*

## Solution
 
Here is the full code-behind file, excluding the standard *using/Imports* statements and the Dynamic Pages Reference region:

````C#
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
````
````VB
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
````

