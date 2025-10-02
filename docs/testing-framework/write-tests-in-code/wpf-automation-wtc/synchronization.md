---
title: Synchronization
page_title: Synchronization
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Synchronization

In the world of testing mostly static HTML pages synchronization was easy. Telerik Testing Framework was even able to automatically take care of synchronization for you (most of the time). All you had to do was click on a button and wait for the browser to be ready, which the framework does behind the scenes for most HTML UI actions.
 
In the world of Silverlight application testing, unlike testing static HTML web pages, you have to intelligently implement synchronization with the Silverlight application under test. This is because in the Silverlight world you're dealing with a real application that is running locally in the browser. The "browser is ready" indicator no longer applies since it only told you when the browser was finished loading the web page from the server.
 
The framework has many features implemented to aid you in synchronizing with your Silverlight application as it's being tested. There are six basic types of waits implemented in the framework that you can use for synchronization:

<table class="docs">
<tr>
	<th>Wait Type</th><th>Description</th>
</tr>
<tr>
	<td>**ForExists**</td><td>This method waits for the element to exist in the Visual Tree. It accepts an optional timeout parameter.</td>
</tr>
<tr>
	<td>**ForExistsNot**</td><td>This method waits for the element to no longer exist in the Visual Tree. It accepts an optional timeout parameter</td>
</tr>
<tr>
	<td>**ForVisible**</td><td>This method waits for the element to both exist in the Visual Tree and its Visibility attribute to equal "Visible". It accepts an optional timeout parameter.</td>
</tr>
<tr>
	<td>**ForVisibleNot**</td><td>This method waits for the Visibility property of the element to not equal 'Visible' or for the element to no longer exist in the Visual Tree. It accepts an optional timeout parameter.</td>
</tr>
<tr>
	<td>**ForNoMotion**</td><td>This method waits for the element to stop moving on the drawing surface. It takes a check interval and an optional timeout parameter.</td>
</tr>
<tr>
	<td>**For(Predicate)**</td><td>This method takes a custom predicate and waits for that predicate to return true. It accepts an optional error message and an optional timeout parameter.</td>
</tr>
<table>

##Waiting for an Element to Exist##

Before you can use the VisualWait.ForExists method to wait for an element to exist you need to create what is called an "Element Proxy". An element proxy is a lightweight FrameworkElement that doesn't actually represent a real element but contains information on how to find the desired element in the Visual Tree. To create an element proxy implement code like this:

```C#
app.Find.Strategy = FindStrategy.WhenNotVisibleReturnElementProxy;
FrameworkElement myElementProxy = app.Find.ByName("MyElement");
```
```VB
app.Find.Strategy = FindStrategy.WhenNotVisibleReturnElementProxy
Dim myElementProxy As FrameworkElement = app.Find.ByName("MyElement")
```

Now that you have an element proxy you use it to wait for the element to exist using this line of code:

```C#
// Wait 15 seconds for the element to exist
proxy.Wait.ForExists(15000);
```
```VB
' Wait 15 seconds for the element to exist
proxy.Wait.ForExists(15000)
```

##Using ForExistsNot, ForVisible, ForVisibleNot,  ForNoMotion##

Using any of these functions is pretty straightforward. Just call the method with appropriate parameters, for example:

```C#
FrameworkElement ticket = app.FindName("airlineTicket");
ticket.Wait.ForExistsNot();         // Wait for the element to no longer exist
ticket.Wait.ForVisible(3000);       // Wait up to 3 seconds for the element to become visible
ticket.Wait.ForVisibleNot(2500);    // Wait up to 2.5 seconds for the element to no longer be visible
ticket.Wait.ForNoMotion(250, 4500); // Wait up to 4.5 seconds for the element to stop moving. Check every 1/4 second.
```
```VB
Dim ticket As FrameworkElement = app.FindName("airlineTicket")
ticket.Wait.ForExistsNot()          ' Wait for the element to no longer exist
ticket.Wait.ForVisible(3000)        ' Wait up to 3 seconds for the element to become visible
ticket.Wait.ForVisibleNot(2500)     ' Wait up to 2.5 seconds for the element to no longer be visible
ticket.Wait.ForNoMotion(250, 4500)  ' Wait up to 4.5 seconds for the element to stop moving. Check every 1/4 second.
```

##Creating Your Own Wait Condition##

If none of the built-in framework wait for methods meet your needs, the framework has the ability to use your own coded conditional predicate instead. This feature relieves you of the burden of having to fully implement your own custom wait loop.
 
You can implement your conditional predicate in a function or a lambda expression. Here is a sample of how to implement and use your own conditional predicate in a function:

```C#
FrameworkElement guideButton = app.FindName("guideButton");
guideButton.Wait.For(myComparator);
 
public bool myComparator(FrameworkElement elem)
{
    return elem.Visibility == ArtOfTest.WebAii.Silverlight.UI.Visibility.Visible;
}
```
```VB
Dim guideButton As FrameworkElement = app.FindName("guideButton")
    guideButton.Wait.[For](AddressOf myComparator)
 
Public Function myComparator(ByVal elem As FrameworkElement) As Boolean
    Return elem.Visibility = ArtOfTest.WebAii.Silverlight.UI.Visibility.Visible
End Function
```


To do the same thing in a lambda expression would look like this:


```C#
FrameworkElement guideButton = app.FindName("guideButton");
guideButton.Wait.For(new System.Predicate<FrameworkElement>((fe) => fe.Visibility == ArtOfTest.WebAii.Silverlight.UI.Visibility.Visible));
```
```VB
Dim guideButton As FrameworkElement = app.FindName("guideButton")
guideButton.Wait.[For](New System.Predicate(Of FrameworkElement)(Function(fe) fe.Visibility = ArtOfTest.WebAii.Silverlight.UI.Visibility.Visible))
```
