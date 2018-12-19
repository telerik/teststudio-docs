---
title: Invoking Javascript
page_title: Invoking Javascript
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/write-tests-in-code/advanced-topics/javascript/invoking-javascript.aspx, /user-guide/write-tests-in-code/advanced-topics/javascript/invoking-javascript
position: 1
---
#Invoking Javascript#

Telerik Testing Framework supports directly invoking JavaScript functions from your .NET test code. One key advantage to this support is that you can use it to do your JavaScript unit testing without having to integrate yet another unit testing framework into your development environment. You can also avoid having to learn/support this additional framework. Abilities include:

* Invoke JavaScript functions and get return values.

* Handle JSON objects returned after invoking a JavaScript function.

* Invoke script events directly on a page element. (e.g. OnBlur(), OnMouseOut(), etc)

* Attach .NET event handlers to actual JavaScript events.

* Perform logging/tracing of your JavaScript routines. The logging is done directly into the unified log you are using.

##Invoking JavaScript Functions##

The Actions.InvokeScript() enables you to simply provide a JavaScript function name to invoke. For example:

```C#
// Assume our page has JavaScript method Test1() & Test2() & Test3()
 
// Call a JavaScript function.
Actions.InvokeScript("Test1()");
 
// Call a JavaScript function with parameters
// NOTE: It is important to enclose literal string parameter with double quote and not single
// quotes. IE will fail if you don't do so.
Actions.InvokeScript(@"Test2(""WebAii"", 4)");
 
// Call a JavaScript function and get its return values
string jsRetValue = Actions.InvokeScript("Test3();");
 
// Call a JavaScript function that returns a value
int val = Actions.InvokeScript<int>(@"Test3(""Bear"", ""Utah"")");
```


```VB
' Assume our page has JavaScript method Test1() & Test2() & Test3()
 
' Call a JavaScript function.
Actions.InvokeScript("Test1()")
 
' Call a JavaScript function with parameters
' NOTE: It is important to enclose literal string parameter with double quote and not single
' quotes. IE will fail if you don't do so.
Actions.InvokeScript("Test2(""WebAii"", 4)")
 
' Call a JavaScript function and get its return values
Dim jsRetValue As String = Actions.InvokeScript("Test3();")
 
' Call a JavaScript function that returns a value
Dim val As Integer = Actions.InvokeScript(Of Integer)("Test3(""Bear"", ""Utah"")")
```


Here is a code which calls an Angular function against input field:

```C#
Actions.InvokeScript("angular.element(" + element.ClientSideLocator + ").val('" + text.Replace("'", "\\'") + "').triggerHandler('input')");
```

##JavaScript Unit Testing Using NUnit or Visual Studio Team Test##

Below is an example of how you can define JavaScript unit tests that is consistent with the rest of your tests and manages their execution and reporting using the same unit testing infrastructure, whether it is NUnit or Visual Studio Team Test.


```C#
[TestMethod]
public void JsUnitTest1()
{
    // return 'true' for pass or 'false' for fail.
    string strBool = Actions.InvokeScript("JsUnitTest1()");
    Assert.IsTrue(bool.Parse(strBool));
}
```
 

```VB
<TestMethod()> _
Public Sub JsUnitTest1()
    ' return 'true' for pass or 'false' for fail.
    Dim strBool As String = Actions.InvokeScript("JsUnitTest1()")
    Assert.IsTrue(Boolean.Parse(strBool))
End Sub
```

###See also

* <a href="/advanced-topics/coded-samples/html/jQuery-events-do-not-fire" target="_blank">jQuery events do not fire</a>