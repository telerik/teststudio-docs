---
title: Extend BaseWebAiiTest Class
page_title: Extend BaseWebAiiTest Class - Test Studio Dev Documentation
description: Extend BaseWebAiiTest Class
position: 1
---
# How to Extend BaseWebAiiTest Class Functionality

A possible scenario is to use same functionality in most of the tests in the project. It is possible to implement a method which will be available in each code behind file in the project. The approach to this problem is to extend the <a href="https://docs.telerik.com/teststudioapi/html/T_ArtOfTest_WebAii_Design_BaseWebAiiTest.htm" target="_blank">BaseWebAiiTest</a> class and set all test files to inherit from the new extended class.

The steps to implement such approach are as follows:

1.Create a new project

2.Add a <a href="/code-in-test/features-in-code#Custom-Code" target="_blank">stand alone class file</a> *ExtendedBaseWebAiiTest* which inherits from the abstract class *BaseWebAiiTest*. A sample implementation of such file containing the method *PrintMessage()* is listed below:

````C#

	
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
	````
````VB

	
		Imports ArtOfTest.WebAii.Design
		
		Namespace ExtendBaseWebAiiTestProject
		
			Public Class ExtendedBaseWebAiiTest
				Inherits BaseWebAiiTest
				
				Public Sub PrintMessage(ByVal message As String)
					Log.WriteLine(message)
				End Sub
			End Class
		End Namespace
	````

3.Open the code behind file of any test and modify its class to inherit the newly created _ExtendedBaseWebAiiTest_ class and the _PrintMessage()_ method defined in it will be available for the test. 

````C#

	
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
	````
````VB

	
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
	````
