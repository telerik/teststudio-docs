---
title: Using VS Team Test
page_title: Using VS Team Test
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---

#Using Visual Studio Team Test#

Telerik Testing Framework comes with built-in support for Visual Studio Team Test and its unit testing framework. Telerik Testing Framework can be used with or without Visual Studio, but if you are already using Visual Studio Team Test in your development environment, you can easily and quickly integrate Telerik Testing Framework as part of that environment.
 
Telerik Automation Infrastructure comes with the following features to facilitate its integration with Visual Studio:

* Telerik Testing Framework comes with a BaseTest base test class under its TestTemplates namespace that can be used as the base class for all your Telerik automation tests running as a Visual Studio unit test. The base class provides the following integration features:

* Unifies both the logging location and the log content. Any logging from Telerik automation using its Log object will also be logged to the Visual Studio log location and to the actual Visual Studio log content of that particular test. This includes logging from JavaScipt.

```C#
[TestMethod]
public void DLog()
{
     // logging from VS
     TestContext.WriteLine("Hello from VS");
     // logging from Telerik
     Log.WriteLine("Hello from Telerik");
  
}
```
```VB
<TestMethod()> _
Public Sub DLog()
  
     ' logging from VS
     TestContext.WriteLine("Hello from VS")
     ' logging from Telerik
     Log.WriteLine("Hello from Telerik")
  
End Sub
```

##Visual Studio log##

###VS 2012 / 2013###

![VS 2012/2013][1]

###VS 2010###

![VS 2010][2]

* Telerik settings can be read directly from an **app.config** file contained in your Visual Studio test project. This allows you to configure your Telerik tests using the same .config file that you would be using to store your connection strings and other settings for your test suite.

* When installing Telerik Testing Framework, a new fully commented Visual Studio item template will be added to your list of available templates. This will enable you to start using Telerik Testing Framework by simply selecting it from the 'Add->New Item' tool menu (or context menu) available to your VS project. You are provided with both a C# and a VB.NET template.

##Getting Started Using Visual Studio Team Test##

In this section we will walk you through the steps to get you started using Telerik Framework inside a Visual Studio Team Test environment.

* Once you have completed installing Telerik Testing Framework on the target machine, start your Visual Studio environment and open your test project or create a new test project if you are starting from scratch.

![New project][3]

* Once you have created the project, right-click the project node in the Solution Explorer. Then select Add->New Item... (NOTE: Do not use Add->New Test)

* Visual Studio will pop-up the Add New Item dialog as shown below.

![Add new item][4]

* Expand the Test node displayed on the left then select Telerik Testing Framework. Then choose Web or Wpf. You should see four templates as shown in the image above.

* Select the **VsUnit** template.

* Enter a name for your new unit test file then click Add.

* At this point, you should have a new test added to your project and you should be ready to go. The template will automatically add a reference of **ArtOfTest.WebAii.dll** to your project that contains the Telerik infrastructure and all the initialization and clean-up routines will be setup in your new unit test file.

* Start writing your automated Telerik unit test just like any other Visual Studio unit test. You can view, manage, and execute your Telerik unit tests just like any other Visual Studio unit tests.

##Telerik's Visual Studio Team Test Template##

The Telerik Framework template is very similar to Visual Studio's unit test template with the addition of Telerik's integration points to initialize and clean up Telerik's infrastructure. Telerik Visual Studio tests also inherit from a base test class called **BaseTest** that lives in the **ArtOfTest.WebAii.TestTemplate** namespace. The base class, in addition to providing the integration benefits described above, provides:

* Short-cuts to the commonly used objects within your test code. For example, instead of always typing **Manager.ActiveBrowser.Find**, there is a first class **Find** object exposed off the **BaseTest** that is set to the **Manager.ActiveBrowser.Find** instance. The following are the objects and their short-cuts that the base class provides:

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

[1]: /img/testing-framework/using-vs-team-test/fig1.png
[2]: /img/testing-framework/using-vs-team-test/fig2.png
[3]: /img/testing-framework/using-vs-team-test/fig3.png
[4]: /img/testing-framework/using-vs-team-test/fig4.png