---
title: Attribute Extensions
page_title: Attribute Extensions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Unit Testing Attribute Extensions

## What Are These Extensions?

Unit testing attribute extensions is one of the coolest features of the framework. They came about as we were reviewing automated unit test code for some of our customers and our own unit testing code for the framework. The things that became apparent after reviewing these automated tests were:

* There is a lot of duplicated code across unit tests that perform element searches that are identical. Many tests perform actions against the same elements on the page but apply different test logic and test data. For example a test class for doing input validation for a segment of an application will require each unit test to first locate that input element on the page and then set the test data for that unit test method. This usually results in lots of duplicated code across unit tests for the same application.

* Test code maintenance is a nightmare for large test beds. Element searches (i.e. Find.Byxx) are usually sprinkled all over the test bed and when a shared element changes, you end up having to go through all these tests, locate the Find.Byxx call and update it by hand. Doing global text Find/Replace searches end up being a very tricky and time consuming task.
 
To address these issues we can:

* Move these searches into their own routines. Given the number of element searches within a test bed, that can get out of hand sometimes and it hinders a bit the legibility of the test code.

* Use the FindParam serialization described under FindParams as External XML Data Sources. Although this is our recommended approach, we wanted to introduce an intermediate step that is agile, quick, and easy to understand that customers can step into to facilitate the complete move to external FindParam data sources.
 
These conclusions lead us to the introduction of unit testing attribute specific extensions to NUnit & Visual Studio Team Test.
 
Attribute Extensions are test fixture attributes that can be used to decorate unit test methods or classes to describe FindParam objects and dialog handling. These attributes are automatically understood and handled by the framework's automation infrastructure. These test fixture attributes live under the 'ArtOfTest.WebAii.TestAttributes' namespace:

* **FindParamAttribute**: You use this attribute to describe how an element can be found on the page. You set this attribute on test methods or share it across all test methods of a particular test class by setting it on the test class that contains the test methods that will use the FindParam definitions.

* **DialogAttribute**: You use this attribute on test methods to define the Win32 pop-up dialogs you want monitored and define how you want them handled. If you have common dialogs that pop-up across your test methods, you can simply set this attribute on the test class and the dialog will be monitored and handled for all test methods contained in that test class.

## Examples

### FindParamAttribute

Let's start by taking few examples for FindParamAttribute. Assume we have an input textbox that we commonly access through out all the test methods in our Foo test class. Well, we can share this methods across all the test methods in 'foo' by setting that FindParam using FindParamAttribute on the test class like this:


````C#
[TestClass]
[FindParam("InputTxtbx", FindType.TagIndex, "input:0")]
class Foo : BaseTest
{
     [DeploymentItem("Pages\\WebExtensions.htm"), TestMethod]
     public void WebExtTest1()
     {
         Manager.LaunchNewBrowser();
         ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME));
 
         // Set the text of the textbox
         Actions.SetText(Find.Elements["InputTxtbx"], "test1");
     }
 
     [DeploymentItem("Pages\\WebExtensions.htm"), TestMethod]
     public void WebExtTest3()
     {
         Manager.LaunchNewBrowser();
         ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME));
 
         // Set the text of the textbox
         Actions.SetText(Find.Elements["InputTxtbx"], "test2");
     }
}
````
 

````VB
<TestClass(), _
FindParam("InputTxtbx", FindType.TagIndex, "input:0")> _
Public Class Foo
    Inherits BaseTest
 
    <TestMethod(), _
    DeploymentItem("Pages\\WebExtensions.htm")> _
    Public Sub WebExtTest1()
 
        Manager.LaunchNewBrowser()
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME))
 
        ' Set the text of the textbox
        Actions.SetText(Find.Elements("InputTxtbx"), "test1")
 
    End Sub
 
    <TestMethod(), _
    DeploymentItem("Pages\\WebExtensions.htm")> _
    Public Sub WebExtTest3()
 
        Manager.LaunchNewBrowser()
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME))
 
        ' Set the text of the textbox
        Actions.SetText(Find.Elements("InputTxtbx"), "test2")
 
    End Sub
 
End Class
````

You can use 1-N FindParam attributes on your test class or test method. If you have elements that are shared across more than one test method, set these FindParam's on the test class, else simply set them on the test method. For example:

````C#
[TestClass]
[FindParam("InputTxtbx", FindType.TagIndex, "input:0")]
class Foo : BaseTest
{
     [TestMethod]
     [DeploymentItem("Pages\\WebExtensions.htm")]
     [FindParam("CheckBx", FindType.AttributesOnly, "", "id=chk1")]
     public void WebExtTest2()
     {
         Manager.LaunchNewBrowser();
         ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME));
 
         // Set the text of the textbox
         Actions.SetText(Find.Elements["InputTxtbx"], "test1");
 
         // Verify the table
         Actions.Check(Find.Elements["CheckBx"], true);
     }
 
     [TestMethod]
     [DeploymentItem("Pages\\WebExtensions.htm")]
     public void WebExtTest3()
     {
         Manager.LaunchNewBrowser();
         ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME));
 
         // Set the text of the textbox
         Actions.SetText(Find.Elements["InputTxtbx"], "test2");
         Assert.AreEqual<string>("test2", Find.Elements["InputTxtbx"].GetValue<string>("value"));
 
         // NOTE:
         // "CheckBx" is not accessible from the Find.Elements[] collection
         // here. Calling Find.Elements["CheckBx"], will throw an exception.
     }
}
````
 

````VB
<TestClass(), _
FindParam("InputTxtbx", FindType.TagIndex, "input:0")> _
Public Class Foo
    Inherits BaseTest
 
    <TestMethod(), _
    DeploymentItem("Pages\\WebExtensions.htm"), _
    FindParam("CheckBx", FindType.AttributesOnly, "", "id=chk1")> _
    Public Sub WebExtTest2()
 
        Manager.LaunchNewBrowser()
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME))
 
        ' Set the text of the textbox
        Actions.SetText(Find.Elements("InputTxtbx"), "test1")
 
        ' Verify the table
        Actions.Check(Find.Elements("CheckBx"), True)
 
    End Sub
 
    <TestMethod(), _
    DeploymentItem("Pages\\WebExtensions.htm")> _
    Public Sub WebExtTest3()
 
        Manager.LaunchNewBrowser()
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDeploymentDir, TEST_PAGE_NAME))
 
        ' Set the text of the textbox
        Actions.SetText(Find.Elements("InputTxtbx"), "test2")
 
        ' NOTE:
        ' "CheckBx" is not accessible from the Find.Elements[] collection
        ' here. Calling Find.Elements["CheckBx"], will throw an exception.
 
    End Sub
 
End Class
````

### FindParamAttributes and TestRegions

FindParamAttributes can also be used with TestRegions when they are defined within an application. In this scenario, the FindParam needs to reflect an element search within a specific TestRegion. To tie a FindParamAttribute with a TestRegion, simply set the TestRegionId property of that FindParam on your test method or test class. Here is an example:

FindParamAttributes can also be used with TestRegions when they are defined within an application. In this scenario, the FindParam needs to reflect an element search within a specific TestRegion. To tie a FindParamAttribute with a TestRegion, simply set the TestRegionId property of that FindParam on your test method or test class. Here is an example:

````C#

[TestMethod]
[Description("Illustrate how to use FindParamAttributes with TestRegion's")]
[FindParam("progtbl", FindType.TagIndex, "table:1")]
[FindParam("progtbltr", FindType.TagIndex, "table:0", TestRegionId="ProgramsTable")]
public void UsingFindParamAttributeWithTestRegion's()
{
     Manager.LaunchNewBrowser();
     ActiveBrowser.NavigateTo(TESTPAGE);
 
     // FindParam attributes can be associated to a specific TestRegion.
     // When a TestRegionId is specified, only the Find object off that region
     // object can be used to access that element. The search will be scoped
     // to that region also.
 
     // Two FindParam attribues are defined on this method. Both point to the
     // same element on the page.
     // The first is generic can be accessed using the ActiveBrowser.Find object.
     // The second can be accessed only using the ProgramsTable.Find object.
     TestRegion ProgramsTable = ActiveBrowser.Regions["ProgramsTable"];
 
     Assert.IsTrue(this["progtbl"].Equals(this.Elements["progtbltr"]));
 
     // Note: You can also use the FindParamAttribute(fileName) and scope all
     // the elements contained in file to a specific testregion.
}
````
 

````VB
<TestMethod(), _
Description("Illustrate how to use FindParamAttributes with TestRegion's"), _
FindParam("progtbl", FindType.TagIndex, "table:1"), _
FindParam("progtbltr", FindType.TagIndex, "table:0", TestRegionId:="ProgramsTable")> _
Public Sub UsingFindParamAttributeWithTestRegions()
 
     Manager.LaunchNewBrowser()
     ActiveBrowser.NavigateTo(TESTPAGE)
     ' FindParam attributes can be associated to a specific TestRegion.
     ' When a TestRegionId is specified, only the Find object off that region
     ' object can be used to access that element. The search will be scoped
     ' to that region also.
     ' Two FindParam attribues are defined on this method. Both point to the
     ' same element on the page.
     ' The first is generic can be accessed using the ActiveBrowser.Find object.
     ' The second can be accessed only using the ProgramsTable.Find object.
     Dim ProgramsTable As TestRegion = ActiveBrowser.Regions("ProgramsTable")
     ' Contains only the element defined and scoped to "ProgramsTable";
     Assert.IsTrue(this.Elements("progtbl").Equals(this.Elements("progtbltr")))
     ' Note: You can also use the FindParamAttribute(fileName) and scope all
     ' the elements contained in the file to a specific testregion.
 
End Sub
````

### DialogAttribute

Dialog attribute is used similar to the FindParamAttribute but instead of defining how an element should be found, it defines how a dialog should be handled in addition to the dialog types to handle. Again these attributes can be shared across test methods by setting them on a test class or can be directly set on the test method that will cause the dialog to pop up. Here are few examples of some of the common dialogs:

````C#
// ALERTS
[TestMethod]
[Dialog(DialogButton.OK)] // handle any alert dialogs in this test method
public void AlertDialogsUsingAttributes()
{
     // Invoke an alert dialog
     Actions.InvokeScript("InvokeAlert()");
}
 
// FILE UPLOAD
[TestMethod]
[FindParam("uploadfile", FindType.TagIndex, "input:0")]
[Dialog(Globals.PATH_TO_PAGES + @"..\SupportFiles\EmptyTextFile.txt", DialogButton.OPEN)]
public void FileUpLoadDialogUsingAttributes()
{
     // Cause the upload Dialog to pop-up
 
     // With Firefox, it is no allowed to pop the dialog using script due to security restrictions.
     if (ActiveBrowser.BrowserType == BrowserType.FireFox)
     {
         // invoke the dialog using a direct mouse click (Click 10 pixels to the left of the right edge of the control)
         Desktop.Mouse.Click(MouseClickType.LeftClick, Find.Elements["uploadfile"].GetRectangle(),
         new Point(-10, 0), OffsetReference.RightCenter);
 
         // Given that we are using pure UI outside the browser, let's make sure we wait for the browser to
         // be ready
         ActiveBrowser.WaitUntilReady();
     }
     else
     {
         // just click it
         Actions.Click(Find.Elements["uploadfile"]);
     }
}
 
// LOG ON
[TestMethod]
[Dialog("<username>","<password>", DialogButton.OK)]
public void LogonDialogWithAttributes()
{
     // Navigate to a page that needs a logon
     ActiveBrowser.NavigateTo(http://www.test.com/pageneedinglogon.aspx);
}
````
 

````VB

' Alerts
<TestMethod(), _
Dialog(DialogButton.OK)> _
Public Sub AlertDialogsUsingAttributes()
     ' Invoke an alert dialog
     Actions.InvokeScript("InvokeAlert()")
End Sub
 
' File Upload
<TestMethod(), _
Dialog((Globals.PATH_TO_PAGES + "..\SupportFiles\EmptyTextFile.txt"), DialogButton.OPEN)> _
Public Sub FileUpLoadDialogUsingAttributes()
     ' Cause the upload Dialog to pop-up
     ' With Firefox, it is not allowed to pop the dialog using script due to security restrictions.
     If (ActiveBrowser.BrowserType = BrowserType.FireFox) Then
         ' invoke the dialog using a direct mouse click (Click 10 pixels to the left of the right edge of the control)
         Desktop.Mouse.Click(MouseClickType.LeftClick, Find.Elements("uploadfile").GetRectangle, New Point(-10, 0), OffsetReference.RightCenter)
         ' Given that we are using pure UI outside the browser, let's make sure we wait for the browser to
         ' be ready
         ActiveBrowser.WaitUntilReady()
     Else
         ' just click it
         Actions.Click(Find.Elements("uploadfile"))
     End If
End Sub
 
' Log on
<TestMethod(), _
Dialog("<username>", "<password>", DialogButton.OK)> _
Public Sub LogonDialogWithAttributes()
     ActiveBrowser.NavigateTo("<Place a Url to LogOn to here>")
End Sub
````
**Note:** All examples shown above should work with NUnit 2.4 and higher and Visual Studio Team Test. In the samples above we simply used Visual Studio Team Test.
