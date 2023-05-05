---
title: Multi-Browser Support
page_title: Multi-Browser Support
description: "Test Studio Testing framework support for multiple browser instances."
previous_url: /user-guide/write-tests-in-code/advanced-topics/multi-browser-instance-support.aspx, /user-guide/write-tests-in-code/advanced-topics/multi-browser-instance-support
position: 1
---
#Multi-Browser Instance Support#

Throughout the Telerik Testing Framework tutorials, we've been focusing only on the single browser instance 'ActiveBrowser,' given that it is the most common usage in web automation. Multi-browser instance automation within one session of the Manager object is supported, however. Having different types of browsers being automated within the same session is also supported. For example, within one test case session, you can automate two Internet Explorer browser instances and one Firefox instance all running concurrently. Such types of automation might not be very common but might be useful for certain specialized scenarios. (i.e. you could use this feature to do bitmap comparison across different browser types by capturing browser images from one instance and comparing it to the captured image from another instance).

##How It Works##

The 'Manager' object is the main object that keeps tracks of all active browser instances using the Manager.Browsers[] collection. Users can launch as many instances as they want by using the 'Manager.LaunchNewBrowser()' method. Each time a new browser is launched, the 'Manager' creates the new 'Browser' object corresponding to that browser instance and adds it to the Browsers[] collection. The 'ActiveBrowser' property exposed off the 'Manager' is actually the last launched browser and should be the last browser instance in the 'Browsers[]' collection.

**Note:** Manager.LaunchNewBrowser() when called with no parameters, launches the browser type set in the passed in Settings object. You can explicitly set the browser type you want launched by specifying it using the Manager.LaunchNewBrowser(BrowserType type) overload.
 
The below sample demonstrates how you can leverage the multi-browser support to automate multiple instances of a browser within one test case. Such testing might be needed when performing concurrency testing in your web app.

```C#
// Launch a new instance of IE
Manager.LaunchNewBrowser(BrowserType.InternetExplorer, true);
  
// Set this instance to active browser
Browser ie = Manager.ActiveBrowser;
  
// Launch a new instance of Firefox
Manager.LaunchNewBrowser(BrowserType.FireFox, true);
  
// set this instance to the active browser.
// Note how ActiveBrowser is always set to the last launched instance
Browser ff = Manager.ActiveBrowser;
  
// Launch another instance of Firefox
Manager.LaunchNewBrowser(BrowserType.FireFox, true);
   
// set this instance. Note how we can also use the Browser[] collection instead of
// using the ActiveBrowser.  // in this 
Browser ff2 = Manager.Browsers[Manager.Browsers.Count - 1];
  
// you can then uses these instances just like you would use the 'ActiveBrowser' instance.
ie.NavigateTo("http://www.google.com");
ff.NavigateTo("http://www.google.com");
ie.NavigateTo("http://www.live.com");
ff2.NavigateTo("http://www.kayak.com");
  
// You can also use the Window property off each browser to manipulate the
// actual browser window
ie.Window.SetFocus();
  
// close the first firefox instance
// Note: Although the Window class off each browser object has a .close() method,
// it is recommended to use the Browser.Close() method when closing browser instances
// since it will also perform the disconnect and clean-up from the manager properly.
// You can also choose to set a timeout as shown below to double check that the
// browser has actually closed and its handle is no longer visible.
ff.Close(40);
```
```VB
' Launch a new instance of IE
Manager.LaunchNewBrowser(BrowserType.InternetExplorer, True)
  
' Set this instance to active browser
Dim ie As ArtOfTest.WebAii.Core.Browser = Manager.ActiveBrowser
  
' Launch a new instance of Firefox
Manager.LaunchNewBrowser(BrowserType.FireFox, True)
   
' set this instance to the active browser.
' Note how ActiveBrowser is always set to the last launched instance
Dim ff As ArtOfTest.WebAii.Core.Browser = Manager.ActiveBrowser
  
' Launch another instance of Firefox
Manager.LaunchNewBrowser(BrowserType.FireFox, True)
  
' set this instance. Note how we can also use the Browser[] collection instead of
' using the ActiveBrowser.  ' in this 
Dim ff2 As ArtOfTest.WebAii.Core.Browser = Manager.Browsers(Manager.Browsers.Count - 1)
  
' you can then uses these instances just like you would use the 'ActiveBrowser' instance.
ie.NavigateTo("http://www.google.com")
ff.NavigateTo("http://www.google.com")
ie.NavigateTo("http://www.live.com")
ff2.NavigateTo("http://www.kayak.com")
  
' You can also use the Window property off each browser to manipulate the
' actual browser window
ie.Window.SetFocus()
  
' close the first firefox instance
' Note: Although the Window class off each browser object has a .close() method,
' it is recommended to use the Browser.Close() method when closing browser instances
' since it will also perform the disconnect and clean-up from the manager properly.
' You can also choose to set a timeout as shown below to double check that the
' browser has actually closed and its handle is no longer visible.
ff.Close(40)
```