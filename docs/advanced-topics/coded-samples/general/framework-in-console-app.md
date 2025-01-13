---
title: Framework in Console App
page_title: Framework in Console App
description: "Test Studio - create a console application that performs UI automation tasks by using the Telerik Testing Framework."
position: 1
---
# Create a Console Application that Utilizes the Telerik Testing Framework

*I would like to create a console application that performs UI automation tasks by using the Telerik Testing Framework. This application can run without the use of a test runner. It cannot be considered a real "test," but an application that utilizes a specific API.*

## Solution

**Note**: At a minimum, the Telerik Testing Framework or Run-Time Edition must be installed on the machine where you intend to run the test.

First, create a C# or Visual Basic Console application project. The project is generated with an initial class that contains the Main function. A Console app begins executing from this function.
 
In order to access the Telerik Testing Framework API, add the necessary assembly references. Depending on the type of application, add the following assemblies:


* HTML

	* Telerik.Webaii.Controls.Html
	* Telerik.Webaii.Controls.Html
	* ArtOfTest.Webaii.Design


* Silverlight

	* Telerik.Webaii.Xaml
	* ArtOfTest.Webaii
	* ArtOfTest.Webaii.Design

* WPF

	* Telerik.Webaii.Xaml.WPF
	* ArtOfTest.Webaii
	* ArtOfTest.Webaii.Design 


These assemblies can be found in Telerik's installation folder. These assemblies can be found in the following two locations on a 64-bit Windows 7 machine:

* **C:\Program Files (x86)\Progress\Test Studio\Bin\**

* **C:\Program Files (x86)\Progress\Test Studio\Bin\Translators\**

 

If you're not sure where to look for the assemblies, perform a Windows search inside the Telerik folder.

Once you've added the assembly references, change the .NET Framework version of the project to 3.5 (if not set already). <a href="http://msdn.microsoft.com/en-us/library/bb398202.aspx" target="_blank">Here</a> is how to do that (go to second section: Changing the Target .NET Framework Version or Profile for an Existing Project). Now you can access the Telerik Testing Framework API from any class inside your project.

The application gets values from *Yahoo! Finance* and outputs them to the console screen. Here's the sole class that holds the logic for the application:

````C#
class Program
    {
        //The URL to navigate to
        static readonly string url = "http://finance.yahoo.com/";
 
        // The symbols to capture
        static readonly string[] symbols = { "NYMT", "FEED.PK", "AGNC", "NLY", "INTC " };
        // define how to find the target elements
        static readonly string txtInputExpr = "id=txtQuotes";
        static readonly string submitExpr = "value=Get Quotes";
        static readonly string table1Expr = "id=table1";
        static readonly string table2Expr = "id=table2";
 
        static void Main(string[] args)
        {
           // Settings settings = new Settings(new Settings.WebSettings(BrowserType.InternetExplorer));
 
            Manager myMgr = new Manager(new Settings());
            myMgr.Start();
            myMgr.LaunchNewBrowser();
            myMgr.ActiveBrowser.NavigateTo(url);
 
            HtmlInputText txtInput = myMgr.ActiveBrowser.Find.ByExpression<HtmlInputText>(txtInputExpr);
            HtmlInputSubmit submit = myMgr.ActiveBrowser.Find.ByExpression<HtmlInputSubmit>(submitExpr);
 
            foreach (string symbl in symbols)
            {
                txtInput.Text = symbl;
                submit.Click();
                HtmlTable table1 = myMgr.ActiveBrowser.Find.ByExpression<HtmlTable>(table1Expr);
                HtmlTable table2 = myMgr.ActiveBrowser.Find.ByExpression<HtmlTable>(table2Expr);
                Console.WriteLine(symbl + ": " + table1.BodyRows[0].Cells[1].InnerText + " Vol: " + table2.BodyRows[2].Cells[1].InnerText);
            }
            myMgr.Dispose();
 
            Console.WriteLine("\nPress Enter when finished.");
            Console.Read();
        }
    }
````
````VB
 Class Program
        'The URL to navigate to
        Shared ReadOnly url As String = "http://finance.yahoo.com/"
 
        ' The symbols to capture
        Shared ReadOnly symbols As String() = {"NYMT", "FEED.PK", "AGNC", "NLY", "INTC "}
        ' define how to find the target elements
        Shared ReadOnly txtInputExpr As String = "id=txtQuotes"
        Shared ReadOnly submitExpr As String = "value=Get Quotes"
        Shared ReadOnly table1Expr As String = "id=table1"
        Shared ReadOnly table2Expr As String = "id=table2"
 
 
        Shared Sub RunTest()
 
            ' Settings settings = new Settings(new Settings.WebSettings(BrowserType.InternetExplorer));
 
            Dim myMgr As New Manager(New Settings())
            myMgr.Start()
            myMgr.LaunchNewBrowser()
            myMgr.ActiveBrowser.NavigateTo(url)
 
            Dim txtInput As HtmlInputText = myMgr.ActiveBrowser.Find.ByExpression(Of HtmlInputText)(txtInputExpr)
            Dim submit As HtmlInputSubmit = myMgr.ActiveBrowser.Find.ByExpression(Of HtmlInputSubmit)(submitExpr)
 
            For Each symbl As String In symbols
                txtInput.Text = symbl
                submit.Click()
                Dim table1 As HtmlTable = myMgr.ActiveBrowser.Find.ByExpression(Of HtmlTable)(table1Expr)
                Dim table2 As HtmlTable = myMgr.ActiveBrowser.Find.ByExpression(Of HtmlTable)(table2Expr)
                Console.WriteLine(symbl + ": " + table1.BodyRows(0).Cells(1).InnerText + " Vol: " + table2.BodyRows(2).Cells(1).InnerText)
            Next
            myMgr.Dispose()
 
            Console.WriteLine(vbLf & "Press Enter when finished.")
            Console.Read()
        End Sub
    End Class
````