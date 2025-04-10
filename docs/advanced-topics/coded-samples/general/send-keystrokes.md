---
title: Send Keystrokes
page_title: Send Keystrokes
description: "Send key press or combination of key presses in Test Studio test run. "
previous_url: /user-guide/code-samples/general/send-keystrokes.aspx, /user-guide/code-samples/general/send-keystrokes
position: 1
---
# Send Keystrokes

## Problem 1

*I want to press Enter key.*

## Solution 1

This is possible with a coded solution:

1. <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2. Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

````C#
using System.Windows.Forms;
 
namespace TestProject8
{     
    public class SendKeystrokes : BaseWebAiiTest    {  
        
     
        [CodedStep(@"New Coded Step")]
         public void Keystrokes()
        {                
            Manager.Desktop.KeyBoard.KeyPress(Keys.Enter);
        }
    }
}
````
````VB
Imports System.Windows.Forms
 
Namespace TestProject8
    Public Class SendKeystrokes
        Inherits BaseWebAiiTest
         
        <CodedStep("New Coded Step")> _
        Public Sub KeyStrokes()

            Manager.Desktop.KeyBoard.KeyPress(Keys.Enter)
         
        End Sub
    End Class
End Namespace
````

## Problem 2

*I want to type text with keystrokes.*

## Solution 2

This is possible with a coded solution:

1. <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2. Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

````C#
using System.Windows.Forms;
 
namespace TestProject8
{     
    public class SendKeystrokes : BaseWebAiiTest    {  
        
     
        [CodedStep(@"New Coded Step")]
         public void Keystrokes()
        {
            Manager.Desktop.KeyBoard.TypeText("InputValue");
        }
    }
}
````
````VB
Imports System.Windows.Forms
 
Namespace TestProject8
    Public Class SendKeystrokes
        Inherits BaseWebAiiTest
         
        <CodedStep("New Coded Step")> _
        Public Sub KeyStrokes()
 
        Manager.Desktop.KeyBoard.TypeText("InputValue")
        
        End Sub
    End Class
End Namespace
````


> <a href="http://msdn.microsoft.com/en-us/library/system.windows.forms.sendkeys(v=vs.110).aspx" target="_blank">Here</a> you can find the list with key codes.

## Problem 3

*I want to perform combination of key presses like Ctrl+A.*

## Solution 3

This is possible with a coded solution:

1. <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2. Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

````C#
using System.Windows.Forms;
 
namespace TestProject8
{     
    public class SendKeystrokes : BaseWebAiiTest    {  
        
     
        [CodedStep(@"New Coded Step")]
         public void Keystrokes()
        {
           Manager.Desktop.KeyBoard.KeyPress(Keys.Control | Keys.X);     
        }
    }
}
````
````VB
Imports System.Windows.Forms
 
Namespace TestProject8
    Public Class SendKeystrokes
        Inherits BaseWebAiiTest
         
        <CodedStep("New Coded Step")> _
        Public Sub KeyStrokes()

            Manager.Desktop.KeyBoard.KeyPress(Keys.Control | Keys.X)
            
        End Sub
    End Class
End Namespace
````

