---
title: WPF UI Automation
page_title: WPF UI Automation
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/write-tests-in-code/silverlight-test-automation/wpf-test-automation.aspx, /user-guide/write-tests-in-code/silverlight-test-automation/wpf-test-automation
position: 2
---
#Getting started with WPF UI Automation

To get started, let's use a simple application and demo some basic automation scenarios like button click and set text. Then we will expand into more advanced topics and scenarios. Let's take the following simple application that contains a button and a text box. When you click the button, it simply changes "Push the button" to "Hello world!" in the text box. The application looks like this:

![WPF app][1]

To automate the application above to set the text, click the button and then verify the hello text in **Telerik Testing Framework**, we can simply write the following code using the **WPF Extension** (which resides under **ArtOfTest.WebAii.Wpf**). The template for this method is based on a VsUnit test. However, the code itself can be reused in other type of Unit tests - it's just the template that will be different.

```C#
[TestMethod]
public void wpfDemo()
   {
	// Launch the application instance from its location in file system
    WpfApplication wpfApp = Manager.Current.LaunchNewApplication(@"C:\Projects\WpfApplication2\bin\Debug\WpfApplication2.exe");
   
	// Validate the title of the main window
    Assert.IsTrue(wpfApp.MainWindow.Window.Caption.Equals("MainWindow"));
   
	//Get the button
    Button b =   wpfApp.MainWindow.Find.ByName<Button>("button1");
   
	//Click the button 
    b.User.Click();
   
	//Get the text box
    TextBox tb = wpfApp.MainWindow.Find.ByName<TextBox>("textBlock1");
   
	//Verify the text
    Assert.IsTrue(tb.Text.Equals("Hello World!"));
   
    }
```
```VB
<TestMethod> _
  Public Sub wpfDemo()
   ' Launch the application instance from its location in file system
   Dim wpfApp As WpfApplication = Manager.LaunchNewApplication("C:\Projects\WpfApplication2\bin\Debug\WpfApplication2.exe")
   
   ' Validate the title of the main window
      Assert.IsTrue(wpfApp.MainWindow.Window.Caption.Equals("MainWindow"))
   
   'Get the button
   Dim b As Button = wpfApp.MainWindow.Find.ByName(Of Button)("button1")
   
   'Click the button 
      b.User.Click()
   
   'Get the text box
   Dim tb As TextBox = wpfApp.MainWindow.Find.ByName(Of TextBox)("textBlock1")
   
   'Verify the text
      Assert.IsTrue(tb.Text.Equals("Hello World!"))
   
  End Sub
```


Let's take a closer look at the code above line by line:

* Line 5 (*WpfApplication wpfApp = Manager.LaunchNewApplication(@"C:\Projects\WpfApplication2\bin\Debug\WpfApplication2.exe");*)

	This is basic code that launches the application from a location on the local machine and initializes it into a variable for us. As soon as you have an instance of a Wpf App,you now have full access to the application including the entire Logical Tree. 

* Line 8 ( *Assert.IsTrue(wpfApp.MainWindow.Window.Caption.Equals("MainWindow"));*)

	We use the standard Assert class to check the name of the **MainWindow**. The MainWindow is a member of the generic WpfApplication class since every application has one and it holds its entire content.

* Line 11 (*Button b = wpfApp.MainWindow.Find.ByName\<Button>("button1");*)

	The **MainWindow** offers a short-cut member '**Find**' which contains search-related methods. In the above sample, given that the **Button** has a name associated with it, we can use **Find.ByName** to locate it. The MainWindow class offers two versions of **Find.ByName**:

	* The first is a generic method that can return any Framework element.

	* The second version allows you to specify the specific type of Framework Element you're looking for and will only return element of the specified type.
 
	We'll be using the specific version.

* Line 14 (*b.User.Click();*)

	We are using the '**User**' object to click the button. The User object is present on all elements that inherit from **FrameworkElement** and offers real user interactions with WPF elements. So a click using the 'User' object will actually move the mouse over that button and click it. That is exactly what this line does.

* Line 17 (*TextBox tb = wpfApp.MainWindow.Find.ByName\<TextBox>("textBlock1");*)

	Similarly to line 11 we initialize the Texbox from the app into a variable after locating it by name.

* Line 20 (*Assert.IsTrue(tb.Text.Equals("Hello World!"));*)

	Now that the button is clicked, we need to verify that the message is correct.
 
	Now that we understand this sample, let's dig into some of the key objects available in the WPF Extension.

[1]: /img/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/wpf-ui-automation/fig1.png
