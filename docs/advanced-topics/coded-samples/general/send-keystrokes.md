---
title: Send Keystrokes
page_title: Send Keystorkes
description: "Send keystrokes like Alt+F4 in Test Studio test run. How to automate holding down the Ctrl key + performing selection in Test Studio test run"
previous_url: /user-guide/code-samples/general/send-keystrokes.aspx, /user-guide/code-samples/general/send-keystrokes
position: 1
---
#Send Keystorkes#

*I want to send keystrokes like Alt+F4.*


##Solution##

This is possible with a coded solution:

1. <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2. Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

```C#
using System.Windows.Forms;
 
namespace TestProject8
{     
    public class SendKeystrokes : BaseWebAiiTest    {  
        
     
        [CodedStep(@"New Coded Step")]
         public void Keystrokes()
        {
            Manager.Desktop.KeyBoard.SendString("%{F4}");
        }
    }
}
```
```VB
Imports System.Windows.Forms
 
Namespace TestProject8
    Public Class SendKeystrokes
        Inherits BaseWebAiiTest
         
        <CodedStep("New Coded Step")> _
        Public Sub KeyStrokes()
 
        Manager.Desktop.KeyBoard.SendString("%{F4}")
        
        End Sub
    End Class
End Namespace
```


> <a href="http://msdn.microsoft.com/en-us/library/system.windows.forms.sendkeys(v=vs.110).aspx" target="_blank">Here</a> you can find the list with key codes.

*I want to perform multi-select while holding down the Ctrl key.*

##Solution##

This is possible with a coded solution:

1. <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*.
2. Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the test.

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

```C#
using System.Windows.Forms;
 
namespace TestProject8
{     
    public class SendKeystrokes : BaseWebAiiTest    {  
        
     
        [CodedStep(@"New Coded Step")]
         public void Keystrokes()
        {
            
                
                Manager.Desktop.KeyBoard.KeyDown(Keys.Control);
 
                //You can put the click steps HERE
 
                Manager.Desktop.KeyBoard.KeyUp(Keys.Control);
        }
    }
}
```
```VB
Imports System.Windows.Forms
 
Namespace TestProject8
    Public Class SendKeystrokes
        Inherits BaseWebAiiTest
         
        <CodedStep("New Coded Step")> _
        Public Sub KeyStrokes()
             
            Manager.Desktop.KeyBoard.KeyDown(Keys.Control)
 
            'You can put the click steps HERE
 
            Manager.Desktop.KeyBoard.KeyUp(Keys.Control)
 
        
        End Sub
    End Class
End Namespace
```

