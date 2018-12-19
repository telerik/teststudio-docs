---
title: Using Elements From Elements Repository In A Utility Class
page_title: Using Elements From Repository In A Utility Class
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#How to Use Elements From Repository In A Utility Class#

*I would like to use elements recorded in the <a href="/knowledge-base/project-configuration-kb/element-repository" target="_blank">Elements repository</a> in my standalone code class file.*

##Solution##

We do not recommend using elements from the repository in a <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone class file</a>. If there is a specific scenario you could not avoid you could refer to the example below. You would need to add references to ***ArtOfTest.WebAii.Core.dll*** and ***ArtOfTest.WebAii.Design.dll*** and include *using* statements for these in the code file. The ***Utility class*** inherits the ***BaseWebAiiTest*** and requires definition for region ***[Dynamic Pages Reference]***.

```C#
using ArtOfTest.WebAii.Core;
using ArtOfTest.WebAii.Design;

namespace SomeTestProject
{
    public class Utility : BaseWebAiiTest 
    {
        #region [ Dynamic Pages Reference ]
        
        private Pages _pages;
 
        public Pages Pages
        {
            get
            {
                if (_pages == null)
                {
                    _pages = new Pages(Manager.Current);
                }
                return _pages;
            }
        }
        #endregion
        
        public void DoSomething()
        {
            Pages.Bing.SbFormQSearch.Text = "Cat" ;
            Pages.Bing.SbFormGoSubmit.Click();
        }
    }
}
```

```VB
Imports ArtOfTest.WebAii.Core
Imports ArtOfTest.WebAii.Design

Namespace SomeTestProject
	Public Class Utility
		Inherits BaseWebAiiTest
		#Region "[ Dynamic Pages Reference ]"

		Private _pages As Pages

		Public ReadOnly Property Pages() As Pages
			Get
				If _pages Is Nothing Then
					_pages = New Pages(Manager.Current)
				End If
				Return _pages
			End Get
		End Property
		#End Region

		Public Sub DoSomething()
			Pages.Bing.SbFormQSearch.Text = "Cat"
			Pages.Bing.SbFormGoSubmit.Click()
		End Sub
	End Class
End Namespace

```

In a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> you would need to create an instance of this class in order to use its methods as shown below:

```C#
// create an instance of the class
var MyClass = new Utility();

// call a method of this class
MyClass.DoSomething();
```

```VB
// create an instance of the class
Dim [MyClass] = New Utility()

// call a method of this class
[MyClass].DoSomething()
```
