---
title: Utility Class In Test Studio Standalone
page_title: Utility Class In Test Studio Standalone
description: "Utility Class Helper class file In Test Studio Standalone project"
previous_url: /user-guide/code-samples/general/utility-in-standalone.aspx, /user-guide/code-samples/general/utility-in-standalone
position: 1
---
# How To Use A Utility Class In Test Studio Standalone Version #

## Problem ##

*I would like to create/use global variables and/or functions in Test Studio Standalone version and access these from all tests within the current project.*

## Solution ##

<a href="/features/coded-steps/standalone-code-file" target="_blank">Here</a> you could read how to create a standalone code file within a Test Studio project. Below are listed two examples how a class file named *Utility* could be adjusted to cover two  common scenarios: ***write text to external file*** and ***perform certain action against an element***. The provided sample code requires reference to ***System.IO.dll*** and  ***ArtOfTest.WebAii.Controls.HtmlControls.dll*** added in the project settings and the respective *using* statements in the code. Note that the namespace of the standalone code file must be the same as the namespace of the project.

```C#
using System.IO;
using ArtOfTest.WebAii.Controls.HtmlControls;

namespace YourTestProjectNamespace
{
	public static class Utility
	{
     	//variable accessible from each test in project
     	public static int valueHolder;

     	//method accessible from each test in project, writes text in external file
     	public static void WriteToFile(string path, string content)
     	{
        	//write the passed string argument to a file
        	StreamWriter file = new StreamWriter(path);
        	file.WriteLine(content);
        	file.Close();
		}

		//method accessible from each test, clicks on an element
        public static void ClickOnElement(HtmlControl element)
        {
            element.MouseClick();
        }
	}
}
```
```VB
Imports System.IO
Imports ArtOfTest.WebAii.Controls.HtmlControls

Namespace YourTestProjectNamespace
	Public NotInheritable Class Utility

		'variable accessible from each test in project
		Public Shared valueHolder As Integer

		'method accessible from each test in project, writes text in external file
		Public Shared Sub writeToFile(path As String, content As String)

			'write the passed string argument to a file

			Dim file As New StreamWriter(path)
			file.WriteLine(content)
			file.Close()

		End Sub

		'method accessible from each test, clicks on an element
		Public Shared Sub clickOnElement(element As HtmlControl)
			
			element.MouseClick()

		End Sub
	End Class
End Namespace
```

Once the code file is ready for use compile the project to build the assembly. Then you'll be able to access the functions/variables within your *Utility* class from all tests in this project. Note that the Test Studio code editor will not auto-complete references to the contents of the *Utility* class.

### How To Use Methods And Variables From The Utility Class File ###

The code sample below demonstrates how the global methods and variables could be accessed in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a>. 

```C#
//set value to the global variable
Utility.valueHolder = 2;

//write value to test log
Log.WriteLine("Value from Utility class:" + Utility.valueHolder.ToString());

//invoke function, creates a new file and writes in it the string variable passed 
Utility.WriteToFile(@"c:\myNewText200.txt", "some content");

//locate a button with id=controlId
HtmlControl searchBtn = Find.ById<HtmlControl>("controlId");

//call Utility class method to perform click on element using the predefined static function
Utility.ClickOnElement(searchBtn);
```
```VB
Utility.valueHolder = 2

Log.WriteLine("Value from Utility class:" + Utility.valueHolder.ToString())

Utility.writeToFile("c:\myNewText200.txt", "some content")

Dim searchBtn As HtmlControl = Find.ById(Of HtmlControl)("sb_form_go")

Utility.clickOnElement(searchBtn)
```