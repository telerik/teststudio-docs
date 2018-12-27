---
title: Javascript Logging
page_title: Logging from JavaScript
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
#Logging from JavaScript#

Telerik Testing Framework also supports logging directly from JavaScript into the unified test log that your tests are using. Logging from JavaScript is not enabled by default and needs to be explicitly enabled globally by setting the **Settings.EnableScriptLogging = true** via the <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/settings-and-configuration-wtc/settings-class" target="_blank">Settings Class</a> or setting **enableScriptLogging="true"** in the application <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/settings-and-configuration-wtc/app-config-file" target="_blank">.config</a> file. In addition each page that wants to perform logging needs to include the WebAii_Logging.js file. You will find this file installed in the %InstallDir%\Bin folder.
 
Below is a sample to demonstrate how to perform logging from your JavaScript routines:

```C#
// Settings.Current.EnableScriptLogging must be set to true before
// LaunchNewBrowser. This was done in the Initialize section of
// this test.
// Make sure the web page references the WebAii_Logging.js file.
 
// Invoke a function that will perform logging from JavaScript.
Actions.InvokeScript("Test5()");
 
// Verify that we have a log from JavaScript.
Assert.IsTrue(Log.Text.Contains("Test5"));
 
// Disable logging. This won't have any effect until the browser
// is closed and reopened.
Settings.Current.EnableScriptLogging = false;
 
// NOTE: Once script logging is disabled, any logging calls from
// the script will be ignored and won't cause a script error.
```
 

```VB
' Settings.Current.EnableScriptLogging must be set to true before
' LaunchNewBrowser. This was done in the Initialize section of
' this test.
' Make sure the web page references the WebAii_Logging.js file.
 
' Invoke a function that will perform logging from JavaScript.
Actions.InvokeScript("Test5()")
 
' Verify that we have a log from JavaScript.
Assert.IsTrue(Log.Text.Contains("Test5"))
 
' Disable logging. This won't have any effect until the browser
' is closed and reopened.
Settings.Current.EnableScriptLogging = False
 
' NOTE: Once script logging is disabled, any logging calls from
' the script will be ignored and won't cause a script error.
```

The page script function Test5() can perform logging like this:

```JavaScript
function Test5()
{
    WebAiiLog("Trace", "Test5: Log this message!");
}
```
