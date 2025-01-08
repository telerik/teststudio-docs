---
title: Using xUnit
page_title: Using xUnit
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---

# Using xUnit

Telerik Testing Framework comes with built-in support for xUnit.net 1.8 and higher. The latest release of xUnit can be downloaded <a href="http://xunit.codeplex.com/releases/view/62840" target="_blank">here</a>.
 
Telerik Automation Infrastructure comes with the following features to facilitate integration with xUnit.net:

* Telerik Testing Framework comes with a BaseTest base class under its TestTemplates namespace that can be used as the base class for all your Telerik automation tests running under xUnit.net. The base class provides the following integration features:

* Telerik settings can be read directly from the app.Config of your test project. This allows you to configure your Telerik tests using the same .config file that you might be using to store your connection strings or other settings for your test suite.

* When installing Telerik Testing Framework, a new fully commented xUnit.net item template will be added to your list of available templates. This will enable you to start using Telerik by simply selecting it from the Add->New Item tool menu (or context menu) available to your VS project. You are provided with both a C# and a VB.NET template.

## Getting Started Using xUnit.net

In this section we will walk you through the steps to get you started using Telerik Testing Framework with xUnit.net.

* Once you have completed installing Telerik Testing Framework on the target machine, start your Visual Studio environment and open your xUnit.net test library in Visual Studio or create a new one if you are starting from scratch.

* Once you have created the project, select the project node in the Solution Explorer and right-click. Then select **Add->New Item...** (**NOTE:** Do not use Add->New Test)

* Visual Studio will pop-up the **Add New Item** dialog as shown below.

![Create xUnit project][1]

* Expand the Test node displayed on the left then select Telerik Testing Framework. You should see four templates as shown in the image above.

* Select the **xUnit** template.

* Enter a name for your test and click **Add**.

* At this point, you should have a new test added to your project and you should be ready to go. The template will automatically add a reference of **ArtOfTest.WebAii.dll** to your project that contains the Telerik infrastructure and all the initialization and clean-up routines will be setup in your new unit test file.

* If you haven't already done so, you'll need to manually add a reference to the xunit.dll.

* Start writing your automated Telerik Testing Framework unit tests.

## Telerik's xUnit Template

Telerik xUnit.net tests inherit from a base test class called **BaseTest** that lives in the **ArtOfTest.WebAii.TestTemplate** namespace. The base class, in addition to providing the integration benefits described above, provides:

* Short-cuts to the commonly used objects within your test code. For example, instead of always typing **Manager.ActiveBrowser.Find**, there is a first class **Find** object exposed off the **BaseTest** class that is set to the **Manager.ActiveBrowser.Find** instance. The following are the objects and their short-cuts that the base class provides:

<table class="docs">
<tr>
	<th>Object reference</th><th>Shortcut name</th>
</tr>
<tr>
	<td>Manager.ActiveBrowser</td>
	<td>ActiveBrowser</td>
</tr>
<tr>
	<td>Manager.ActiveBrowser.Find</td>
	<td>Find</td>
</tr>
<tr>
	<td>Manager.ActiveBrowser.Actions</td>
	<td>Actions</td>
</tr>
<tr>
	<td>Manager.Desktop</td>
	<td>Desktop</td>
</tr>
<tr>
	<td>Manager.Log</td>
	<td>Log</td>
</tr>
<tr>
	<td>Manager</td>
	<td>Manager</td>
</tr>
</table>

* Takes care of creating the Manager object and setting up all the above short cuts.

* Reads the .config file (if available) and reads the Telerik settings from it and initializes Telerik Testing Framework according to these settings.

* The base class also offers different options that you might want to choose from depending on the scenarios and your testing environment. The Telerik template installed on your machines, by default uses the following initialization:

```C#
Initialize(false);
```
```VB
Initialize(False)
```

The above initialization initializes the Telerik Testing Framework but does not enable the RecycleBrowser feature. Because xUnit.net does not have the concept of a test fixture setup/teardown the RecycleBrowser feature cannot be used. If that initialization does not work for you, you can choose to pass in different parameters or choose to do your own custom setup of the framework. For example, if you want to override some of the settings from the .config file in one or two of your test cases, you can simply do the following:

```C#
// This will get a new Settings object. If a configuration
// section exists, then settings from that section will be
// loaded
  
Settings settings = GetSettings();
  
// Override the settings you want. For example:
settings.DefaultBrowser = BrowserType.FireFox;
  
// Now call Initialize with your updated settings object
Initialize(settings);
```
```VB
' This will get a new Settings object. If a configuration
' section exists, then settings from that section will be
' loaded
  
Dim mySettings As Settings = GetSettings()
  
' Override the settings you want. For example:
mySettings.DefaultBrowser = BrowserType.FireFox
  
' Now call Initialize with your updated settings object
Initialize(mySettings)
```

For more information on Telerik Testing Framework's settings & configuration please refer to the <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/settings-and-configuration-wtc/settings-class" target="_blank">Settings and Configuration</a> topic.

## Starting Automation


```C#
[Test]
[Description("My simple demo")]
public void SimpleTest()
{
     // Launch an instance of the browser
     Manager.LaunchNewBrowser();
  
     // Navigate to google.com
     ActiveBrowser.NavigateTo("http://www.google.com");
  
     // verify the title is actually Google.
     Assert.AreEqual("Google", ActiveBrowser.Find.ByTagIndex("title", 0).InnerText);
}
```
```VB
<Test(), _
Description("My simple demo")> _
Public Sub SimpleTest()
  
     ' Launch an instance of the browser
     Manager.LaunchNewBrowser()
  
     ' Navigate to google.com
     ActiveBrowser.NavigateTo("http://www.google.com")
  
     ' verify the title is actually Google.
     Assert.AreEqual("Google", ActiveBrowser.Find.ByTagIndex("title", 0).InnerText)
  
End Sub
```

[1]: /img/testing-framework/using-xunit/fig1.png