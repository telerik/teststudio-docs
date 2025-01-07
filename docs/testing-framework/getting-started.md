---
title: Getting Started
page_title: Getting Started
description: "Test Studio Testing Framework introduction on how to get started with coded automation tests."
position: 0
---

<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
table-layout: fixed;
width: 930px;
}
table.docs th {
color:#fff;
background-color:#ed8200;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>

#Getting Started with Telerik Testing Framework

Thanks for using Telerik Testing Automation infrastructure. To get started using this framework, please follow the instructions below. If you have further questions, feel free to <a href="http://www.telerik.com/account/support-tickets/available-support-list.aspx" target="_blank">contact us</a>.


##Installing and Setting Up the Infrastructure

To get started, first download the <a href="https://www.telerik.com/teststudio/testing-framework" target="_blank">Telerik Testing Framework</a> installer package and run the installation. Once it is complete, you will have all of the following placed in the Telerik Testing Framework %InstallDir% folder:

* The Telerik Automation Infrastructure library. **ArtOfTest.WebAii.dll** (for version 2010 and older, **ArtOfTest.Common.dll** is also included).

* Telerik's Internet Explorer client. **ArtOfTest.InternetExplorer.dll**.

* Telerik's Firefox client: Automatically installed in your install directory.

* Chrome: You should download and install manually Telerik <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> Chrome Playback extension from the <a href="https://chrome.google.com/webstore/category/extensions" target="_blank">Chrome Web Store</a>. See <a href="/troubleshooting-guide/browser-inconsistencies-tg/extensions-disabled-in-chrome" target="_blank">this article</a> for direct extension links.

* Safari client: Automatically installed in your install directory.

* Silverlight plug-in: **ArtOfTest.WebAii.Mime.dll**.

* Our HTTP Proxy: **ArtOfTest.WebAii.HttpProxy.exe**.

* ASP.NET TestRegion Custom Control: **ArtOfTest.WebAii.AspNet.dll**.

* Visual Studio item templates for VS Team Test, NUnit, MbUnit and xUnit (Both VB.NET and C#). **These are automatically registered with Visual Studio**.

* 90+ Unit Test Code Samples to help illustrate the different features of the Telerik Testing Framework. You will find 4 zipped solutions: (QuickStarts_NUnit_CS.zip, QuickStarts_VSTS_CS.zip, QuickStarts_NUnit_VB.zip, QuickStarts_VSTS_VB.zip). You can use the sample solution that fits your language and testing framework of preference.

* Release notes: **ReleaseNotes.txt**

* API Reference help file. **Documentation.chm**

* Link to the online Documentation including the Getting Started Guide.

* Link to the online community forums.

* Link to Telerik Premier Support description.

> Both the Telerik Testing Framework library and the Internet Explorer client are installed and ready to use once the installation is complete. The templates are also installed into your local templates for the current user. You also have a copy of these templates under %InstallDir%\Visual Studio Templates\.

##Starting Automation Using Telerik Testing Framework

* If you are using Visual Studio Team Test, please reference the <a href="/testing-framework/using-vs-team-test" target="_blank">Studio Team Test</a> Using Visual  topic.

* If you are using NUnit, please reference the <a href="/testing-framework/using-nunit" target="_blank">setup</a> Using NUnit topic.

* If you are not using NUnit or Visual Studio Team Test, you can still use Telerik Testing Framework from a Console Application, a Class Library, or a Windows Application. Simply follow the rest of the instructions below. 

	**Note:** For Visual Studio 2010, change the solution's "Target Framework" property to **.NET Framework 3.5** or **.NET Framework 4.0**. The Client Profile Frameworks will not work.

Once <a href="https://www.telerik.com/teststudio/testing-framework" target="_blank">Testing Framework</a> is installed on the target machine, you can easily start using it from your .NET project by simply referencing the ArtOfTest.WebAii.dll (and ArtOfTest.Common.dll for version 2010 and older) file placed in your %InstallDir%. Those are the only dll's you need to reference to get the full functionality. To reference the Telerik library:

1. Select your project in the Solution Explorer in Visual Studio, or start a new project.

2. Right-click the References folder displayed in the solution and select 'Add Reference'.

3. Navigate to the **ArtOfTest.WebAii.dll** installed on your machine in your %InstallDir%\bin folder.

4. Select ArtOfTest.WebAii.dll (and ArtOfTest.Common.dll for version 2010 and older).

5. Click OK to finish adding the needed references.

##Quick Start Sample Code

Before calling into any of the Telerik library methods, you need to make sure that you have properly initialized an instance of the **Manager** object passing in the settings you want used for this instance. To initialize the project:

```C#
// Initialize the settings
Settings mySettings = new Settings();
 
// Set the default browser
mySettings.Web.DefaultBrowser = BrowserType.InternetExplorer;
 
// Create the manager object
Manager myManager = new Manager(mySettings);
 
// Start the manager
myManager.Start();
 
// Launch a new browser instance. [This will launch an IE instance given the setting above]
myManager.LaunchNewBrowser();
 
// Navigate to a certain web page
myManager.ActiveBrowser.NavigateTo("http://www.google.com");
 
// Perform your automation actions.
Element mybtn = myManager.ActiveBrowser.Find.ByTagIndex("input", 3);
myManager.ActiveBrowser.Actions.Click(mybtn);
 
// Shut-down the manager and do all clean-up
myManager.Dispose();
```
```VB


Dim mySettings As New Settings()
 

mySettings.Web.DefaultBrowser = BrowserType.InternetExplorer
 

Dim myManager As New Manager(mySettings)
 

myManager.Start()
 

myManager.LaunchNewBrowser()
 

myManager.ActiveBrowser.NavigateTo("http://www.google.com")
 

Dim mybtn As Element = myManager.ActiveBrowser.Find.ByTagIndex("input", 3)
myManager.ActiveBrowser.Actions.Click(mybtn)
 

myManager.Dispose()
```

The Manager object exposes all methods/properties needed to perform browser automation, element identification, logging and DOM traversal including TestRegion identification. Below is a brief description of the key objects exposed off the Manager and their corresponding key object properties/methods:

<table class="docs">
<tr>
	<th>Object</th><th>Type Name</th><th>Brief Description</th><th>Key Objects/Methods Exposed</th><th>Quick Start Tutorials</th>
</tr>
<tr>
	<td><b>Manager.<br>ActiveBrowser</b></td>
	<td>ArtOfTest.WebAii.
Core.Browser</td>
	<td>The most recent launched browser instance. You can use it to invoke actions, access the loaded document DOM and perform element identification and extraction using the Browser.Find object.</td>
	<td>Browser.Actions, Browser.Find, Brower.DomTree, Browser.Window</td>
	<td><a href="/testing-framework/automate-browser-actions" target="_blank">Automating Browser Actions</a>, <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">Finding Page Elements</a>, <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/multi-browser-support" target="_blank">Multi-Browser Instance Support</a>, <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/javascript-wtc/invoking-javascript" target="_blank">JavaScript Support</a></td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.Actions</b></td>
	<td>ArtOfTest.WebAii.
Core.Actions</td>
	<td>Used to invoked direct DOM actions against the loaded document.</td>
	<td>Actions.Click, Actions.SetText, Actions.Check, Actions.WaitForElement</td>
	<td><a href="/testing-framework/automate-browser-actions" target="_blank">Automating Browser Actions</a>, <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/ajax-support" target="_blank">Ajax Support</a>, <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/javascript-wtc/invoking-javascript" target="_blank">JavaScript Support</a></td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.Find</b></td>
	<td>ArtOfTest.WebAii.<br>Core.Find</td>
	<td>Used to search the DOM elements of the associated browser.</td>
	<td>Find.SearchRegion</td>
	<td><a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">Finding Page Elements</a>, <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/introduction" target="_blank">Introduction to TestRegions</a>, <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/find-param-as-xml-data" target="_blank">FindParams as External Xml DataSource</a></td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.DomTree</b></td>
	<td>ArtOfTest.WebAii.
Core.TreeBuilder</td>
	<td>The full DOM Tree of the currently loaded document.</td>
	<td>TreeBuilder.TestRegion's, TreeBuilder.Root</td>
	<td><a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">Finding Page Elements</a></td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.Window</b></td>
	<td>ArtOfTest.WebAii.
Win32.Window</td>
	<td>The window representation of this browser window. Use this object to manipulate the browser window and capture bitmaps.</td>
	<td>Window.Handler, Window.GetBitmap()</td>
	<td><a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/win32-windows" target="_blank">Native Win32 Windows Handling</a>, <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/visual-capturing" target="_blank">Visual Capturing</a></td>
</td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.Frames</b></td>
	<td>ArtOfTest.WebAii.
Core.FramesCollection</td>
	<td>Retrieves a list of the child frames contained in the browser window.</td>
	<td>ById, BySrc, RefreshAllDomTrees, WaitUntilReady()</td>
	<td><a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/frames-support" target="_blank">Frames Support</a></td>
</tr>
<tr>
	<td><b>Manager.
ActiveBrowser.Regions</b></td>
	<td>ArtOfTest.WebAii.ObjectModel.
TestRegionCollection</td>
	<td>Retrieves a list of the test regions identified in the DOM.</td>
	<td>Count, Item, Items</td>
	<td><a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/introduction" target="_blank">Introduction to TestRegions</a>, <a href="/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control" target="_blank">Using Asp.Net TestRegion Control</a></td>
</td>
<tr>
	<td><b>Manager.<br>Desktop</b></td>
	<td>ArtOfTest.WebAii.<br>Core.Desktop</td>
	<td>Used to invoke pure UI automation events from the Mouse & Keyboard.</td>
	<td>Desktop.Mouse, Desktop.Keyboard</td>
	<td><a href="/testing-framework/automate-browser-actions" target="_blank">Automating Browser Actions</a></td>
</td>
<tr>
	<td><b>Manager.<br>Log</b></td>
	<td>ArtOfTest.WebAii.<br>Core.Log</td>
	<td>Provides logging support for the current manager session.</td>
	<td>Log.WriteLine, Log.CaptureBrowser()</td>
	<td>none</td>
</td>
</tr>
</table>