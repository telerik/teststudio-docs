---
title: Visual Capturing
page_title: Visual Capturing
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Visual Capturing#


##Visual Capturing of Browser States and Win32 Windows##

Each Telerik Testing Framework Window object provides functionality to capture the visual bitmaps of the actual window it represents. You can capture the entire window or a targeted portion of that window using the Window.GetBitmap() method. You can use this method for any Win32 window represented by the Window object. Lets take a quick example:


```C#
// Get the current browser window bitmap.
System.Drawing.Bitmap browserImage = ActiveBrowser.Window.GetBitmap();
```
```VB
Dim browserImage As System.Drawing.Bitmap = ActiveBrowser.Window.GetBitmap()
```

The Log uses the above method to capture the browser window when calling the Log.CaptureBrowser() method. The log also saves the captured bitmap to the 'LogLocation' as provided by your settings and a line is added to the log file that points to that bitmap file. The bitmaps are also added to the Log.CapturedBitmaps[] array. For example:


```C#
// Capture the bitmap of my current ActiveBrowser and save it to the LogLocation
// [LogLocation is set using the Settings object that is passed in to the Manager's constructor]
Manager.Log.CaptureBrowser(Manager.ActiveBrowser);
  
// Note: If you are automating multiple browser instances, you can simply
// call the CaptureBrowser() passing in any instance from the Manager.Browser[] collection.
```
```VB
Manager.Log.CaptureBrowser(Manager.ActiveBrowser)
```

##Visual Capturing of Elements##

In addition to capturing the entire window, you can also capture targeted portions of that window. Such functionality can be extremely useful when combined with the functionality provided by each DOM element in Telerik Testing Framework. For example, you can use the Element.GetRectangle() to get the coordinates of a specific element and pass that to the Window.GetBitmap(targetRectangle) to visually capture that element. You can then do bitmap comparisons of that element to a base line or even compare it across browsers.
 
Let's take a simple example to demonstrate this functionality. Assume we have the following simple page:

```HTML
<html>
   <head>
    <title>Visual Capturing sample</title>
   </head>
   <body>
    <div style="background-color:Red;width:200px;height:200px;text-align:center;">
       Don't Capture ME
     </div>
     <div id="mydiv" style="background-color:Yellow;width:200px;height:200px;text-align:center;">
       Capture ME
     </div>
    <div style="background-color:Green;width:200px;height:200px;text-align:center;">
       Don't Capture ME
     </div>
    <div style="background-color:Blue;width:200px;height:200px;text-align:center;">
       Don't Capture ME
     </div>
   </body>
</html>
```

The above page renders as follows:

![Site][1]

The below code shows how we can get the visual capture of the second 'div' element:

```C#
// Get the element
Element myDiv = ActiveBrowser.Find.ById("mydiv");
  
// Capture it visually as a bitmap
System.Drawing.Bitmap divimage = ActiveBrowser.Window.GetBitmap(myDiv.GetRectangle());
```
```VB
' Get the element
Dim myDiv As Element = ActiveBrowser.Find.ById("mydiv")
  
' Capture it visually as a bitmap
Dim divimage As System.Drawing.Bitmap = ActiveBrowser.Window.GetBitmap(myDiv.GetRectangle())
```

The divimage bitmap captured object is:

![Captured div][2]

**Note:** If the image is not scrolled properly, the capture won't work. Make sure you use the Browser.Actions.ScrollToVisible() method to ensure the element is visible before capturing it.

[1]: /img/testing-framework/write-tests-in-code/intermediate-topics-wtc/visual-capturing/fig1.png
[2]: /img/testing-framework/write-tests-in-code/intermediate-topics-wtc/visual-capturing/fig2.png
