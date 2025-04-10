---
title: HTML Popups
page_title: HTML Popups
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
# Handling HTML Pop-ups

HTML Pop-up are simply browser instances that are invoked by some action on an element of the page. These pop-ups are mostly invoked by calling window.open() from JavaScript. Customers use this method to prompt the user for information without interrupting the current browser instance the user is working in or to simply open new web pages in new browser instances to show side or detailed information.
 
Given that these pop-ups are just like any other browser instance, the framework enables access to them using the Manager.Browsers[] collection similar to how it enables access to new browser instances launched using the Manager.LaunchNewBrowser() method.
 
Given that HTML pop-up dialogs are launched through some actions on the page and not through an explicit call to Manager.LaunchNewBrowser(), the framework has no idea which new browser instances you want connected and added to the Manager.Browsers[] collection versus the ones you want ignored. Therefore, you need to notify the framework about the browser instances that you want to be tracked by enabling new browser tracking. You enable manager tracking by calling:

````C#
Manager.SetNewBrowserTracking(true);
````
````VB
Manager.SetNewBrowserTracking(true)
````

When new browser tracking is enabled, any new browser instance launched on the machine is automatically added to the Manager.Browsers[] collection. In addition the Manager.ActiveBrowser instance is automatically set to the last launched browser instance. You then have full access to that pop-up instance with its full DOM and the ability to execute automation actions against it just like any other browser instance. When the pop-up is closed using Browser.Close(), the instance is removed from the Manager.Browsers[] collection and the ActiveBrowser instance is again automatically re-assigned to the last active Browser object in the Manager.Browsers[] collection.
 
The sample below demonstrates this support. Let's start with the following HTML page that invokes a HTML pop-up:


````HTML
<html>
<head>
    <title>HTMLPopups</title>
    <script type="text/javascript">
    function OpenWindow()
    {
        window.open ('http://www.bing.com',
        'newwindow', 'height=100,width=400, toolbar=no, menubar=no, scrollbars=no, resizable=no,location=no, directories=no,status=no')
    }
    </script>
  
</head>
<body>
    <a onclick="OpenWindow()">Invoke HTML Popup</a>
</body>
</html>
````

The automation code that allows us to connect to that new instance looks like this:

````C#
// Set new browser tracking to enabled.
// This will make all new browser instances connect to
// the Manager.
Manager.SetNewBrowserTracking(true);
  
// Invoke the popup
Actions.Click(mylink);
  
// Wait for the new browser instance to connect.
Manager.WaitForNewBrowserConnect("bing.com", true, 3000);
  
// disable new browser tracking
Manager.SetNewBrowserTracking(false);
  
// At this point the browsers collection should have two
// browser instances. ActiveBrowser should be set 
// to the popup instance.
Assert.IsTrue(Manager.Browsers.Count == 2);
Assert.IsTrue(ActiveBrowser.Url.Contains("bing.com"));
  
// Close the popup
ActiveBrowser.Close();
  
// At this point, the browsers collection should contain
// only one instance and the ActiveBrowser is set to 
// the last launched active instance.
Assert.IsTrue(Manager.Browsers.Count == 1);
Assert.IsTrue(ActiveBrowser.Url.Contains("PAGE_NAME.com"));
````
````VB
' Set new browser tracking to enabled.
' This will make all new browser instances connect to
' the Manager.
Manager.SetNewBrowserTracking(True)

' Invoke the popup
Actions.Click(Find.Elements("mylink"))

' Wait for the new browser instance to connect.
Manager.WaitForNewBrowserConnect("bing.com", True, 3000)

' disable new browser tracking
Manager.SetNewBrowserTracking(True)

' At this point the browsers collection should have two
' browser instances. ActiveBrowser should be set 
' to the popup instance.
Assert.IsTrue(Manager.Browsers.Count = 2)
Assert.IsTrue(ActiveBrowser.Url.Contains("bing.com"))

' Close the popup
ActiveBrowser.Close()

' At this point, the browsers collection should contain
' only one instance and the ActiveBrowser is set to 
' the last launched active instance.
Assert.IsTrue(Manager.Browsers.Count = 1)
Assert.IsTrue(ActiveBrowser.Url.Contains("PAGE_NAME.com"))
````

Sometimes you need to close the popup by clicking on a button instead of just closing the window. Telerik Testing Framework supports this functionality with an additional paramter to the HtmlControl.Click function. By passing in a 'true' the framework expects the window to close. The ActiveBrowser is also set to the browser window that was open prior to the popup opening.

````C#
Find.ById<HtmlInputButton>("button1").Click(true);  // Here we tell the framework that this click causes the browser window to close
````
````VB
Find.ById(Of HtmlInputButton)("button1").Click(True)    ' Here we tell the framework that this click causes the browser window to close
````

