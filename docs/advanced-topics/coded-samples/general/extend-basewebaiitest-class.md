---
title: Extend BaseWebAiiTest Class
page_title: Extend BaseWebAiiTest Class
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# How to Extend BaseWebAiiTest Class Functionality #

A possible scenario is to use same functionality in most of the tests in the project. It is possible to implement a method which will be available in each code behind test files in the project. The approach to this problem is to extend the <a href="https://docs.telerik.com/teststudioapi/html/T_ArtOfTest_WebAii_Design_BaseWebAiiTest.htm" target="_blank">BaseWebAiiTest</a> class and all test files to inherit from the new extended class.

Steps to implement such approach are as follows:

1.&nbsp; Create a new project

2.&nbsp; Add a <a href="/features/coded-steps/standalone-code-file" target="_blank">stand alone class file</a> *ExtendedBaseWebAiiTest* which inherits from the abstract class *BaseWebAiiTest*. A sample implementation of such file containing the method *PrintMessage()* is given below:

```C#
	using ArtOfTest.WebAii.Design;
	
	namespace ExtendBaseWebAiiTestProject
	{
    	public class ExtendedBaseWebAiiTest : BaseWebAiiTest
    	{
			// this method will be available in each test code behind file coded step
        	public void PrintMessage(string message)
        	{
            	Log.WriteLine(message);
        	}
    	}
	}
```
```VB
	Imports ArtOfTest.WebAii.Design
	
	Namespace ExtendBaseWebAiiTestProject
	
	    Public Class ExtendedBaseWebAiiTest
	        Inherits BaseWebAiiTest
	        
	        Public Sub PrintMessage(ByVal message As String)
	            Log.WriteLine(message)
	        End Sub
	    End Class
	End Namespace
```

3.&nbsp; Close the project and edit project settings file (Settings.aiis - located in the project folder) to use *ExtendedBaseWebAiiTest* as a base class to each test in the project as shown on the next screen-shot:

![Settings file][1]

4.&nbsp; Re-open the project, add a WebTest and a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> inside. Then in the step it will be available the *PrintMessage()* defined in the *ExtendedBaseWebAiiTest* class. Below is given a sample of the code behind file of the WebTest.

```C#
	using ArtOfTest.WebAii.Core;
	using ArtOfTest.WebAii.Design.Execution;
	
	namespace ExtendBaseWebAiiTestProject
	{
	    public class WebTest : ExtendedBaseWebAiiTest
	    {
	        [CodedStep(@"Print From ExtendedBaseAiiTest Method")]
	        public void PrintCodedStep()
	        {
	            this.PrintMessage("This is printed from extended base class method");
	        }
	    }
	}
```
```VB
	Imports ArtOfTest.WebAii.Core
	Imports ArtOfTest.WebAii.Design.Execution
	
	Namespace ExtendBaseWebAiiTestProject
	
	    Public Class WebTest
	        Inherits ExtendedBaseWebAiiTest
	        
	        <CodedStep("Print From ExtendedBaseAiiTest Method")>
	        Public Sub PrintCodedStep()
	            Me.PrintMessage("This is printed from extended base class method")
	        End Sub
	    End Class
	End Namespace
```

[1]: /img/advanced-topics/coded-samples/general/extend-BaseWebAiiTest-class/fig1.png
