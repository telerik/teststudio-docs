---
title: Settings Class
page_title: Settings Class
description: "Test Studio Testing Framework Settings class. Use the Setting Class object to control the coded test execution"
previous_url: /user-guide/write-tests-in-code/intermediate-topics/settings-and-configuration/settings-class.aspx, /user-guide/write-tests-in-code/intermediate-topics/settings-and-configuration/settings-class
position: 1
---
#Settings Class#

How the Telerik Testing Framework behaves during a test run is controlled by the settings contained in the Settings object. There are many settings you can take advantage of to modify its behavior to better meet your testing requirements or testing environment. The complete list of settings is detailed in the table below. A few of the more commonly used settings include:

* BaseUrl - Sets the base URL used by the NavigateTo command.

* DefaultBrowser - Controls which browser will be started by the LaunchNewBrowser command.

 
There are a few methods of controlling the settings in the Settings object. Which method you use depends on when and how you want them set in your unit test.

##Initializing the Settings Object Without Using a Telerik Test Template##

If you're not using one of Telerik's test templates (VsUnit, NUnit, MbUnit, xUnit) to create your unit test, you'll need to create your own Settings object and then pass that object as a parameter to the constructor of your Manager object. For example:

```C#
// Create my own Settings object and then modify the defaults
Settings mySettings = new Settings();
mySettings.DefaultBrowser = BrowserType.FireFox;
mySettings.ClientReadyTimeout = 60000;
  
// Use my Settings object to construct my Manager object
Manager myManager = new Manager(mySettings);
``` 
```VB
' Create my own Settings object and then modify the defaults
Dim mySettings As New Settings()
mySettings.DefaultBrowser = BrowserType.FireFox
mySettings.ClientReadyTimeout = 60000
  
' Use my Settings object to construct my Manager object
Dim myManager As New Manager(mySettings)
```

##Initializing the Settings Object When Using a Test Template##

If you're using one of Telerik's test templates (VsUnit, NUnit, MbUnit, xUnit) to create your unit test, you'll need to create your own Settings object in the TestInitialize section (or Setup section if you're using NUnit) and then pass that object as a parameter to the Initialize method of the base class. For example:

```C#
// This will get a new Settings object. If a configuration
// section exists, then settings from that section will be
// loaded
Settings settings = GetSettings();
  
// Override the settings you want. For example:
settings.UseHttpProxy = true;
  
// Now call Initialize again with your updated settings object
Initialize(settings, new TestContextWriteLine(this.TestContext.WriteLine));
```
```VB
' This will get a new Settings object. If a configuration
' section exists, then settings from that section will be
' loaded
Dim settings As Settings = GetSettings()
  
' Override the settings you want. For example:
settings.UseHttpProxy = True
  
' Now call Initialize again with your updated settings object
Initialize(settings, New TestContextWriteLine(AddressOf Me.TestContext.WriteLine))
```

**Note:** Be sure to call Initialize only once. Calling Initialize a second time will simply be ignored and you'll be left wondering why your settings did not take effect.

##Changing Settings On-The-Fly##

Lastly you can modify most of the settings after your test is already initialized and under-way. Here's how you to do that:

```C#
Manager.Settings.AnnotateExecution = true;
Manager.Settings.DefaultBrowser = BrowserType.FireFox;
```
```VB
Manager.Settings.AnnotateExecution = True
Manager.Settings.DefaultBrowser = BrowserType.FireFox
```

**Note:** The following settings can only be set during initialization: AspNetDevServerPort, CreateLogFile, EnableUILessRequestViewing, LocalWebServer, LogLocation, VerboseHttpProxy and WebAppPhysicalPath.

##Using the RecycleBrowser Feature##

The RecycleBrowser feature was added in version 2.0. Using it can significantly speed up running an entire test suite, no more starting and shutting down of the browser for each individual unit test. It works by launching one browser window in the test fixture initialization of your test suite and then constantly reusing that same browser window for all unit tests contained in your test suite.

There are a just a couple of things you need to be aware of to properly use the RecycleBrowser feature:

1.&nbsp; When RecycleBrowser is active, any Manager.LaunchNewBrowser or Browser.Close() calls will be ignored.

2.&nbsp; You must call the base classes ShutDown() method in the test fixture teardown section to properly the browser window at the end of the test suite. If you miss this then browser windows will be left behind after your test suite has finished and exited.

##Restoring Default Settings##

If it ever becomes necessary you can restore all the settings (except for those that can only be set during initialization) back to their default values. Just use the Reset() method of the Settings object. For example:

```C#
Manager.Settings.Reset();
```
```VB
Manager.Settings.Reset()
```

This table lists all of the WebAii framework settings that are available for you to use:

<table class="docs">
<tr>
	<th>Name</th><th>Description</th><th>Possible Values</th><th>Default Value</th>
</tr>
<tr>
	<td>**AnnotateExecution**</td>
	<td>Controls whether or not to highlight/annotate the target elements that the requested action is being executed against. e.g. **Actions.Click(goButton)**;</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**AnnotationMode**</td>
	<td>This read-only setting contains the full physical path to your local ASP.NET development web server (WebDev.WebServer.EXE). It is set by the framework when LocalWebServer is set to "AspNetDevelopmentServer". Otherwise it is an empty string.</td>
	<td></td>
	<td></td>
</tr>
<tr>
	<td>**AspNetDevServerPort**</td>
	<td>Controls the AspNetDevServer (if used) port. If this is not set (-1) a random port will be generated each time the manager is created.</td>
	<td>0 to int.MaxValue</td>
	<td>Random value</td>
</tr>
<tr>
	<td>**BaseUrl**</td>
	<td>Sets the base URL to use for all NavigateTo() commands. When set NavigateTo() should use a relative URL (e.g. "~/default.aspx").</td>
	<td>Any valid URL</td>
	<td>string.Empty</td>
</tr>
<tr>
	<td>**ClientReadyTimeout**</td>
	<td>Timeout used to wait for a client (a browser) to be ready after it is first launched or after executing a command (in milliseconds). For example after launching the browser if the browser is not ready within this timeout the framework will throw a <a href="http://msdn2.microsoft.com/en-us/library/system.timeoutexception%28vs.80%29.aspx" target="_blank">TimeoutException</a>.</td>
	<td>0 to int.MaxValue</td>
	<td>30000</td>
</tr>
<tr>
	<td>**CreateLogFile**</td>
	<td>Gets or sets whether to create a log file on disk. This value is read once at initialization time. Changing this value during test execution has no effect.</td>
	<td>true<br>
	false</td>
	<td>true</td>
</tr>
<tr>
	<td>**DefaultBrowser**</td>
	<td>The default browser (i.e. Internet Explorer or Firefox or AspNetHost) to launch when calling Manager.LaunchNewBrowser().</td>
	<td>"InternetExplorer"<br>
	"FireFox"<br>
	"AspNetHost"<br>
	"Safari"h</td>
	<td>"InternetExplorer"</td>
</tr>
<tr>
	<td>**EnableScriptLogging**</td>
	<td>Globally enables or disables logging of JavaScript execution.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>

<tr>
	<td>**EnableUILessRequestViewing**</td>
	<td>Controls whether or not to allow debugging of UILess page requests using a UI browser like Internet Explorer.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**ExecuteCommandTimeout**</td>
	<td>The amount of time to wait for a response to be received from the browser (in milliseconds) after sending it a command request. For example: if there is no response from the browser within this amount of time after sending it a click request, the framework will throw a <a href="http://msdn2.microsoft.com/en-us/library/system.timeoutexception%28vs.80%29.aspx" target="_blank">TimeoutException</a>.</td>
	<td>0 to int.MaxValue</td>
	<td>20000</td>
</tr>
<tr>
	<td>**ExecutionDelay**</td>
	<td>Sets the amount of execution delay (in milliseconds) between commands. This can help in observing test execution.</td>
	<td>0 to int.MaxValue</td>
	<td>0</td>
</tr>
<tr>
	<td>**IsStressRecordingMode**</td>
	<td>Used internally by Automation Design Canvas only.</td>
	<td></td>
	<td></td>
</tr>
<tr>
	<td>**IsUserInteractiveMode**</td>
	<td>This read-only setting indicates whether or not the currently logged on user is an interactive user. Normally this will always be true unless you are logged in under a non-interactive account. For example, if you create another account on your machine and from your current account launch a process using that other account without interactively logging into that account. That is when this property will be set to false. This is a common scenario when performing continuous integration within a build system and running tests. Usually there is a machine that has an account that VisualStudio simply uses to logon the machine non-interactively, build a product and launch tests.</td>
	<td>true<br>
	false</td>
	<td>Depends on run time environment.</td>
</tr>
<tr>
	<td>**KillBrowserProcessOnClose**</td>
	<td>Gets or sets whether to make sure the browser process is killed when closing the browser. **Note:** Firefox is a single process browser. If you are using multiple browser instances and this setting is on, it will kill all open instances of Firefox.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**LocalWebServer**</td>
	<td>Controls whether or not to use the local ASP.NET development server. When set to true, be sure to set WebAppPhysicalPath to the full physical path of the root of your ASP.NET development server.</td>
	<td>None<br>
	AspNetDevelopmentServer</td>
	<td>None</td>
</tr>
<tr>
	<td>**LogAnnotations**</td>
	<td>Controls whether to log annotations to the log file.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**LogLocation**</td>
	<td>Location where all logging will be performed, both captured bitmaps and WebAii's log file.</td>
	<td>Any valid URI.</td>
	<td>C:\WebAiiLog\</td>
</tr>
<tr>
	<td>**QueryEventLogErrorsOnExit**</td>
	<td>Controls whether or not the Manager object will query Windows Application Event log on exit for any error logged from automation clients. Any errors will be logged to the test log.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**RecycleBrowser**</td>
	<td>When set to true, one instance of the browser will be launched and recycled through out the entire test class and tests until Manager.Dispose is called.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**SimulatedMouseMoveSpeed**</td>
	<td>Sets the simulated mouse move speed for Desktop.Mouse.Move()/DragDrop() operations in pixels/millisecond. Typically values are between 0.1f - 0.5f.</td>
	<td>0 to Single.MaxValue</td>
	<td>0.3</td>
</tr>
<tr>
	<td>**UseHttpProxy**</td>
	<td>Gets/Sets whether to use the built-in http proxy during automation.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**VerboseHttpProxy**</td>
	<td>Gets/Sets whether the HTTP proxy produces lots of tracing output.</td>
	<td>true<br>
	false</td>
	<td>false</td>
</tr>
<tr>
	<td>**WaitCheckInterval**</td>
	<td>Controls the rate that the condition is tested by the HtmlWait class. This value specifies the number of milliseconds to wait between tests of the condition.</td>
	<td>1 to int.MaxValue</td>
	<td>500</td>
</tr>
<tr>
	<td>**WebAppPhysicalPath**</td>
	<td>This setting is used when LocalWebServer is set to 'AspNetDevelopmentServer'. It must be the full physical path to the web application root that you are testing or a path relative to the location of the .config file.</td>
	<td>The full physical path to the web application root.</td>
	<td>string.Empty</td>
</tr>
<table>