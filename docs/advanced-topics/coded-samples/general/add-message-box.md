---
title: Add MessageBox
page_title: Add MessageBox
description: "Add MessageBox in a Test Studio test."
position: 1
---
# Add a MessageBox to a Test

This alert box is a pop-up that is fired at some point and displays text content.

The .NET Framework includes the MessageBox class which offers the intended functionality. In order to access it, you need to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *System.Windows.Forms*. Use the .NET 4.0 version of the assembly. Here's the default location for this assembly on a Windows 7 x64 machine:

**C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.0\Profile\Client**

This implementation is very similar to a pop-up this is fired when Test Studio executes a <a href="/features/custom-steps/manual-step" target="_blank">Manual Step</a>. The only important difference is that the MessageBox can be made to display custom text content. This might come in handy in certain situations - you can use it to perform improvised debugging.

```C#
NativeWindow window = new NativeWindow();
window.AssignHandle(ActiveBrowser.Window.Handle);
MessageBox.Show(window, "This is a message!");
```
```VB
Dim window As New NativeWindow()
window.AssignHandle(ActiveBrowser.Window.Handle)
MessageBox.Show(window, "This is a message!")
```

Here's how to do it in a **WPF Test**:


```C#
NativeWindow window = new NativeWindow();
window.AssignHandle(ActiveApplication.MainWindow.Window.Handle);
MessageBox.Show(window, "This is a message!");
```
```VB
Dim window As New NativeWindow()
window.AssignHandle(ActiveApplication.MainWindow.Window.Handle)
MessageBox.Show(window, "This is a message!")
```


This will pause the test and the alert box will be displayed:

![Messagebox][1]

Test Execution will not continue until you click the button.

Ensure you add the *using* or *Imports* statement to the top of the code-behind file. Click the **View Class** button, scroll to the top of the code, and add this line:

```C#
using System.Windows.Forms;
```
```VB
Imports Windows.Forms;
```

You can use the alert box to display a variety of information. Here's how to display the value of the data source for the current iteration (when using <a href="/features/data-driven-testing/Overview" target="_blank">Data Driven Testing</a>):

```C#
NativeWindow window = new NativeWindow();
window.AssignHandle(ActiveBrowser.Window.Handle);
MessageBox.Show(window, Data["excelColumnName"].ToString());
```
```VB
Dim window As New NativeWindow()
window.AssignHandle(ActiveBrowser.Window.Handle)
MessageBox.Show(window, Data("excelColumnName").ToString())
```

[1]: /img/advanced-topics/coded-samples/general/add-message-box/fig1.png
