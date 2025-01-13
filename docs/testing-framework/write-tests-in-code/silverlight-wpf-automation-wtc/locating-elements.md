---
title: Locating Elements
page_title: Locating Elements
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/write-tests-in-code/silverlight-test-automation/locating-elements.aspx, /user-guide/write-tests-in-code/silverlight-test-automation/locating-elements
position: 3
---
# Locating Elements in Silverlight and WPF applications 

Before you can automate interaction with elements contained in a Silverlight/WPF application, you need to first locate the elements contained within the application. For complex applications, locating elements is probably going to be one of the more time consuming tasks. Testers will need to spend time understanding how to reliably find an element. Silverlight/WPF applications that we studied that rely heavily on control templates and data binding produce quite complex visual trees. Their elements are not easily searchable by **Find.ByName()** given the different <a href=http://msdn.microsoft.com/en-us/library/cc189026%28VS.95%29.aspx" target="_blank">Silverlight</a> and <a href="http://msdn.microsoft.com/en-us/library/ms746659.aspx" target="_blank">WPF</a> name scopes created, and the duplication of names within those templates.

1. <a href="#the-find-strategy">The Find Strategy</a> - change the 'Strategy' property that controls how the method behaves when searching for an element.

2. <a href="#finding-all-elements">Finding All Elements</a> - return a list of the elements contained in the application.

3. <a href="#scoped-searches">Scoped Searches</a> - search for a specific element based on its parent.

4. <a href="#finding-elements-by-xamlfindexpression">Finding Elements by XamlFindExpression</a> - search for an element using a FindExpression.

The simplest method of searching is to use the **Find.ByName(String name)** method or the **Find.ByName\<TControl>(String name)** method. Both methods take a string parameter that specifies the name of the element to locate in the application. The first method returns a FrameworkElement object while the second method returns an object of type T having the specified name. If an element having the specified name does not exist or is not currently visible, or if the found element cannot be cast into type T, the functions will return null ('Nothing' in VB.NET). For example:

````C#
FrameworkElement zoomBox = app.FindName("zoomBox");
TextBox searchText = app.FindName<TextBox>("searchText");
````
````VB
Dim zoomBox As FrameworkElement = app.FindName("zoomBox")
Dim searchText As TextBox = app.FindName(Of TextBox)("searchText")
````

You might be asking "How do I know what name to use to find the element I want?" There really are only a few ways to find out:

1. Refer to the design document of the application. Hopefully the name has been specified.

2. Ask the developer what the name of a particular element is.

3. Examine the source code to find the name.

4. If the above methods are not available to you, you will have to resort to some sort of Silverlight/WPF spy utility such as this one to discover the name.
 
The **Find** object offers a rich set of search methods that enable you to not only find elements using their names, but also by their text or type. Combined with type filtering, LINQ, FrameworkElement navigation, and the Find.AllByXXX routines, you get a rich set of routines that enables you to find any framework element in the tree.
 
All of the common methods for finding an element to operate on are:

<table class="docs">
<tr>
	<th>Method</th><th>Description</th>
</tr>
<tr>
	<td>**Find.ByName()/Find.ByName\<T>**</td><td>Returns the first element having the specified name.</td>
</tr>
<tr>
	<td>**Find.ByText**</td><td>Returns the first TextBlock that matches the text provided.</td>
</tr>
<tr>
	<td>**Find.ByAutomationId**</td><td>Returns an element having the automation ID you specify.</td>
</tr>
<tr>
	<td>**Find.ByType**</td><td>Returns the first element found of the specified type (e.g. Canvas, DataGrid, Calendar).</td>
</tr>
<table>

## The Find Strategy

The Find object has a 'Strategy' property that controls how the method behaves when searching for an element. To change the strategy simply change the Strategy property on the Find object. The following strategies can be set:

<table class="docs">
<tr>
	<th>Strategy</th><th>Description</th>
</tr>
<tr>
	<td>**AlwaysWaitForElementsVisible**</td><td>In this mode the Find object always waits for the element to exist and for its Visibility property to equal "Visible". The default amount of time it will wait is 5 seconds. This timeout can be changed by modifying the Find.Timeout property before using the Find object. This strategy is the default setting.</td>
</tr>
<tr>
	<td>**WhenNotVisibleReturnElementProxy**</td><td>In this mode an 'Element Proxy' is returned if the element cannot be found right away. An 'Element Proxy' is a lightweight FrameworkElement object that only contains information on how to locate the desired element in the Visual Tree. This is useful when you want to use the SilverlightApp.Wait.ForExists method.</td>
</tr>
<tr>
	<td>**WhenNotVisibleReturnNull**</td><td>In this mode null (Nothing in VB.NET) is returned if the element cannot be found right away.</td>
</tr>
<tr>
	<td>**WhenNotVisibleThrowException**</td><td>In this mode a generic exception is thrown if the element cannot be found right away.</td>
</tr>
<table>

## Finding All Elements

Sometimes you may need to fetch a list of the elements contained in the application. Suppose we want a list of all the DataGrids contained in the application. Either of the following lines of code will return this list:


````C#
IList<FrameworkElement> dataGrids1 = app.Find.AllByType("DataGrid");
IList<DataGrid> dataGrids2 = app.Find.AllByType<DataGrid>();
````
````VB
Dim dataGrids1 As IList(Of FrameworkElement) = app.Find.AllByType("DataGrid")
Dim dataGrids2 As IList(Of DataGrid) = app.Find.AllByType(Of DataGrid)()
````

All of the Find.AllByxxx functions are:

<table class="docs">
<tr>
	<th>Method</th><th>Description</th>
</tr>
<tr>
	<td>**Find.AllByName()/Find.AllByName\<T>**</td><td>Find all elements that have a specific name. Allows filtering on a specific control type.</td>
</tr>
<tr>
	<td>**Find.AllByText()**</td><td>Find all TextBlocks that contain a specific text. Use p:text to search for partial text.</td>
</tr>
<tr>
	<td>**Find.AllByType()/Find.AllByType\<T>**</td><td>Find all elements of certain type. i.e Button, Grid..etc. Filtering on type is inherit here.</td>
</tr>
<tr>
	<td>**Find.AllByAutomationID()/Find.AllByAutomationID\<T>**</td><td>Find all elements that have a specific automation ID. Allows filtering on a specific control type.</td>
</tr>
<table>

## Scoped Searches

A more advanced feature is scoped searches. Suppose you need to find the ScrollBar attached to some other element. You would use code like this:


````C#
ScrollViewer searchScroll = app.FindName("patientSearchScroller").Find.ByType<ScrollViewer>();
searchScroll = app.FindName().Find.ByType<>();
````
````VB
Dim searchScroll As ScrollViewer = app.FindName("patientSearchScroller").Find.ByType(Of ScrollViewer)()
searchScroll ScrollViewer = app.FindName().Find.ByType( ScrollViewer)()
````

The above code first locates the element named "patientSearchScroller" and then within that control finds the element of type "ScrollViewer". The search for "ScrollViewer" is considered a scoped search (aka chained search) because the search is limited to only those elements found underneath the "patientSearchScroller" element of the Visual Tree. The FrameworkElement base class has a Find property which allows scoped searches for all elements of an application.

## Finding Elements by XamlFindExpression

Another advanced feature is to find the element using a XamlFindExpression. FindExpressions are the replacement/evolution of FindParams. Telerik Testing Framework uses FindExpressions as the basis for all element searches in the DOM, HWnd, or control trees (including Translator Locators). For example, the above scoped search to retrieve a ScrollViewer can be written using Find.ByExpression as follows:

````C#
ScrollViewer searchScroll = app.Find.ByExpression(new XamlFindExpression("Name=patientSearchScroller", "|", "XamlTag=ScrollViewer")).As<ScrollViewer>();
````
````VB
Dim searchScroll2 As ScrollViewer = app.Find.ByExpression(New XamlFindExpression("Name=patientSearchScroller", "|", "XamlTag=ScrollViewer")).[As](Of ScrollViewer)()
````
