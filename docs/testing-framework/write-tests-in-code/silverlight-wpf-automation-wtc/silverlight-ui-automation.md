---
title: Silverlight UI Automation
page_title: Silverlight UI Automation
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/write-tests-in-code/silverlight-test-automation/introduction.aspx, /user-guide/write-tests-in-code/silverlight-test-automation/introduction
position: 1
---
# Getting Started with Silverlight UI Automation

When thinking about Silverlight applications and automated testing, there are a couple of different approaches that come to mind:
 
To get started, let's use a simple application and demo some basic automation scenarios like button click and set text. Then we will expand into more advanced topics and scenarios. Let's take the following simple Silverlight application that contains a button and a text box. When you click the button, it simply displays hello in a text block on the canvas. The application looks like this:

![Silverlight app][1]

To automate the application above to set the text, click the button and then verify the hello text in Telerik Testing Framework, we can simply write the following code using the Silverlight Extension (which resides under ArtOfTest.WebAii.Silverlight).

````C#
[TestMethod]
public void SLDemo()
{  
	//Enable Silverlight
	Settings.Current.Web.EnableSilverlight = true;
	 
	// Launch a browser instance
	Manager.LaunchNewBrowser();
	 
	// Navigate to the page
	ActiveBrowser.NavigateTo("http://localhost:5697/SilverlightApplication1Web/SilverlightApplication1TestPage.html");
	 
	// Get an instance of our Silverlight app.
	SilverlightApp app = ActiveBrowser.SilverlightApps()[0];
	 
	// Set the text of the text box
	app.FindName<TextBox>("myName").Text = "Telerik";
	 
	// Click the button
	app.FindName<Button>("myBtn").User.Click();
	 
	// Verify the text
	Assert.IsTrue(app.Find.ByTextContent("p:Hello").TextContent.Equals("Hello Telerik"));
}
````
````VB
<TestMethod> _
Public Sub SampleWebAiiTest()
    'Enable Silverlight
    Settings.Current.Web.EnableSilverlight = True
 
    ' Launch a browser instance
    Manager.LaunchNewBrowser()
 
    ' Navigate to the page
    ActiveBrowser.NavigateTo("http://localhost:5697/SilverlightApplication1Web/SilverlightApplication1TestPage.html")
 
    ' Get an instance of our Silverlight app.
    Dim app As SilverlightApp = ActiveBrowser.SilverlightApps()(0)
 
    ' Set the text of the text box
    app.FindName(Of TextBox)("myName").Text = "Telerik"
 
    ' Click the button
    app.FindName(Of Button)("myBtn").User.Click()
 
    ' Verify the text
    Assert.IsTrue(app.Find.ByTextContent("p:Hello").TextContent.Equals("Hello Telerik"))
End Sub
````


Let's take a closer look at the code above line by line:

* Line 8-12

	This is basic code that launches the browser and navigates to a specific page.

* Line 14 (`SilverlightApp app = ActiveBrowser.SilverlightApps()[0];`)

	As soon as you include the Silverlight extension namespace in your test, (**ArtOfTest.WebAii.Silverlight**), the '**SilverlightApps()**' extension method is added to the ActiveBrowser. The extension method offers you a list of all Silverlight applications found on that page. The extension method returns a list that has two accessors. An **index** accessor that takes an int (as shown above) and a string accessor that takes a hostid [The ID of the HTML element that contains the `<object>` tag for the plug-in]. You can pick and choose what works for you. In this sample, given that we only have one Silverlight plug-in on the page, we simply accessed the first and only one.

* Line 17 (`app.FindName<TextBox>("myName").Text = "Telerik";`)

	As soon as you have an instance of a **SilverlightApp**, you now have full access to the application including the entire **VisualTree**. The app offers a short-cut method '**FindName**', that can be used to search the application using an element name. In the above sample, given that the **TextBox** has a name associated with it, we can use FindName to locate it. The SilverlightApp object offers two versions of 'FindName': The first is a generic method that can return a strongly-typed object of the element (As shown above , i.e. a Button, a TextBox, a Grid, etc). The second is simpler and returns the base **FrameworkElement** object. We will discuss the strongly-typed object model offered in Silverlight Extension later.
 
	To go back to the line above, we are simply accessing the **TextBox** that has a name '**myName**' and then setting its Text property to "Telerik". Note that given we are accessing a property on the element, this is analogous to **SetText** on a DOM element in Telerik Testing Framework automation. You are not really typing the text in the textbox but rather setting the Text property inside the application to that text. Our extension enables you to access and set properties directly against any **FrameworkElement**. If we wanted to simulate real typing of the text we would have written code like this:
 
 
	`app.FindName<TextBox>("myName").User.TypeText("Telerik", 50);`

* Line 20 (`app.FindName<Button>("myBtn").User.Click();`)

	Same as above in terms of accessing the button. The difference here is that we are using the '**User**' object to click the button. The **User** object is present on all elements that inherit from **FrameworkElement** and offers real user interactions with Silverlight elements. So a click using the 'User' object will actually move the mouse over that button and click it. That is exactly what this line does.

* Line 23 (`Assert.IsTrue(app.Find.ByTextContent("p:Hello").TextContent.Equals("Hello Telerik"));`) 

	Now that the button is clicked, we need to verify that the message is correct. The difference here is that we can't really use **FindName** to locate the **TextBlock** because the TextBlock doesn't really have a name. The **SilverlightApp** object offers extensive search support within the **VisualTree** beyond FindName() by utilizing similar approach to the Find object off the ActiveBrowser (that is used for HTML DOM searches) but adapted to specific **XAML** search scenarios.
 
	In our code above, we are searching for a TextBlock (All Find.xxText() routines return TextBlocks) that partially contains '**Hello**', hence '**p:Hello**' (Similar to Find.ByContent in HTML search). Once we find the TextBlock, we then verify that the Text of that label is actually 'Hello Telerik' using the **Assert.IsTrue**.

Now that we understand this sample, let's dig into some of the key objects available in the Silverlight Extension.

> There is a new Setting.EnableSilverlight flag that needs to be set to enable WebAii to connect to Silverlight applications. By default this setting is not on. Setting this flag will activate the built-in proxy that we use to detect Silverlight applications.

Limitations:

1. On Vista, if you are automating an external website, then make sure to add the URL to your Trusted Websites list in IE.

2. Our automation supports Silverlight 2.0 (and above). We do not support any previous versions.

3. The automation only supports the **XAP** deployment method.
EnableHtmlAccess needs to be set to 'True' on your application.

4. There are known issues with Silverlight applications that attempt to perform web service calls within the application.

5. EnableHtmlAccess needs to be set to 'True' on your application.

6. The application needs to be running off http:// not C:\...

7. When using localhost as your server name, it must end with a trailing '.' character e.g. http://localhost./.

[1]: /img/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/silverlight-ui-automation/fig1.png
