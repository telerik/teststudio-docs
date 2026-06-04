---
title: Send Keystrokes
page_title: Send Keystorkes - Test Studio Dev Documentation
description: Send Keystorkes
position: 1
---
# Send Keystorkes

*I want to send keystrokes like Alt+F4.*

## Solution

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

````C#
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
````
````VB
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
````

> <a href="http://msdn.microsoft.com/en-us/library/system.windows.forms.sendkeys(v=vs.110).aspx" target="_blank">Here</a> you can find the list with key codes.

*I want to perform multi-select while holding down the Ctrl key.*

## Solution

Here is the full code-behind file, excluding the standard *using/Imports* statements and the *Dynamic Pages Reference* region:

````C#
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
````
````VB
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
````

