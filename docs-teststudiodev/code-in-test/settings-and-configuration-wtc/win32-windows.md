---
title: Win32 Windows
page_title: Win32 Windows
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Native Win32 Windows Handling

Telerik Testing Framework provides generic support for Win32 Windows handling. Under the 'ArtOfTest.Common.Win32' namespace, Telerik Framework provides two key objects that you can use in your test code to generically manage Win32 Windows and Dialogs.

* **WindowManager class**: WindowManager provides your tests a mechanism to enumerate through windows that are children of a specific window handle or all windows that are children of the desktop. The WindowManager exposes the 'GetWindows()' method which you can use to build the enumeration. Once you call GetWindows, the Items collection (exposed by WindowManager) will be populated. Each item in that collection is a Window object.

* **Window class**: The Window class is a wrapper around a Win32 Window handle. The class provides basic properties and methods to gather information from that specific window (i.e. Size, IsMaximized, etc.) and invoke actions on that window (i.e. Close(), Minimize(), GetBitmap(), SetFocus(), etc.).
 
In addition to the functionality described above, the WindowManager exposes a static method 'FindWindowRecursively()' that allows users to search the windows hierarchy recursively looking for a window's caption or classname. Caption search can also be done using a partial caption.
 
Let's take an example to illustrate how these two classes can help provide automation functionality for native Win32 windows:


````C#
Window vsWindow = null;
  
// Get all desktop Windows
// The empty constructor will get all desktop windows because no
// hwnd is specified.
WindowManager winManager = new WindowManager();
winManager.GetWindows();
  
// WinManager.Items is not initialized with all top level windows of the desktop
foreach (Window win in winManager.Items)
{
     if (win.Caption.Contains("Microsoft Visual Studio"))
         vsWindow = win;
  
     Log.WriteLine(string.Format("Window (hwnd:{0},caption:{1},class:{2})",
         win.Handle.ToString(), win.Caption, win.ClassName));
}
  
// Find the vsWindow recursively. Passing IntPtr.Zero will start from the desktop.
Window vsWindowRecur = WindowManager.FindWindowRecursively(
     IntPtr.Zero, "Microsoft Visual Studio", true, 0);
````
 

````VB
Dim vsWindow As Window = Nothing
  
' Get all desktop Windows
' The empty constructor will get all desktop windows because no
' hwnd is specified.
Dim winManager As WindowManager = New WindowManager
winManager.GetWindows()
  
' WinManager.Items is now initialized with all top level windows of the desktop
For Each win As Window In winManager.Items
If win.Caption.Contains("Microsoft Visual Studio") Then
     vsWindow = win
End If
Log.WriteLine(String.Format("Window (hwnd:{0},caption:{1},class:{2})", _
     win.Handle.ToString, win.Caption, win.ClassName))
Next
  
' Find the vsWindow recursively. Passing IntPtr.Zero will start from the desktop.
Dim vsWindowRecur As Window = WindowManager.FindWindowRecursively( _
     IntPtr.Zero, "Microsoft Visual Studio", True, 0)
````

