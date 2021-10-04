---
title: Ajax Support
page_title: Ajax Support
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Ajax Support#

Ajax is one of the latest and fastest growing web development technologies that is fueling today's Web 2.0 era. The technology enables developers to build great and rich web content. However at the same time it adds great complexity to the testing methods required to validate the web applications that use it. To a certain extent, websites that rely heavily on Ajax can no longer rely on using the legacy HTTP record/replay methods to test the entire functionality given that major portions of the website logic are executed within the browser JavaScript engine and in some cases no HTTP requests are being made to the server at all!

Telerik Testing Framework has been built from the ground up with features like Ajax in mind. It supports the following features that help ease the testing and automation authoring for Ajax applications. These features also lay the ground work for a rich, consistent and comprehensive infrastructure that developers and quality assurance professionals can rely on to test rich web content.

* **Direct DOM interaction** with web pages allowing you to perform automation actions from within the browser to automate and exercise your Ajax scripts. This topic is covered in detail under <a href="https://docs.telerik.com/teststudio/testing-framework/automate-browser-actions" target="_blank">Automating Browser Actions</a>.

* **Perform complex UI actions** like DragAndDrop and pure UI actions on web pages (i.e. Hover, Right-click, etc). You have both worlds of automation (DOM + UI) accessible to you using Telerik Framework. This topic is covered in detail under <a href="https://docs.telerik.com/teststudio/testing-framework/automate-browser-actions" target="_blank">Automating Browser Actions</a>.

* **Waiting on DOM changes**. With Ajax, you can no longer rely on the load complete of pages or the browsers ready flag to know when a specific page or scenario has finished. Telerik Framework supports a WaitForElement(s) method exposed off of the Actions object. The WaitForElement(s) allows you to wait for 1-N elements using the rich identification support available. For example, you can wait for an element to show up at a specific DOM location or wait for some of its attributes to be set to certain values, etc. This is covered in more detail below.

* **Retrieve dynamic property values directly from the DOM** of any element hosted by the browser. This is also covered in more detail below.

* **Visual capturing of browser states and elements** to more easily diagnose test failures and application behaviors and do visual comparison of specific elements. This topic is covered in detail under <a href="/code-in-test/settings-and-configuration-wtc/visual-capturing" target="_blank">Visual Capturing</a>.

* **Invoke JavaScript functions** from your test code and perform logging directly from JavaScript. This topic is covered in detail under <a href="/code-in-test/advanced-topics-wtc/javascript-wtc/invoking-javascript" target="_blank">JavaScript Invocation</a> and <a href="/code-in-test/advanced-topics-wtc/javascript-wtc/javascript-logging" target="_blank">JavaScript Logging</a>.

* **Invoke JavaScript events** directly from your test code. For example, invoke the OnBlur() event on an element or the OnMouseOut(), etc. This topic is covered in detail under <a href="/code-in-test/advanced-topics-wtc/javascript-wtc/javascript-events" target="_blank">JavaScript Events</a>.

* **Attach event handlers** directly to JavaScript events. This topic is covered in detail under <a href="/code-in-test/advanced-topics-wtc/javascript-wtc/javascript-events" target="_blank">JavaScript Events</a>.

##Waiting on DOM Changes: WaitForElement(s)##

**WaitForElement**(s) is a great method to use when trying to suspend test execution until a certain element is present or has changed or a specific value of a certain attribute for an element has been set (or even a combination of values). This is a common scenario when automating Ajax applications. WaitForElement(s) requires a basic understanding of <a href="/code-in-test/element-identification/find-param-objects" target="_blank">FindParams and how to define them</a>. Once you know how to craft FindParam's, you will be able to write custom and rich wait routines using a consistent pattern.
 
Let's examine a couple of examples to illustrate how WaitForElement(s) is used. Assume that you are waiting for a table to be inserted in your DOM tree at a certain location and you want to wait until the whole table is built including the sixth row. The following is the DOM segment before the Ajax call is made:

```HTML
<!--testregion id="ajaxupdate"-->
<div>
</div>
<!--/testregion-->
```

Here is the DOM after the call has been made:


```HTML
<!--testregion id="ajaxupdate"-->
<div>
  <table>
     <tr><td>Data</td></tr>
     <tr><td>Data</td></tr>
     <tr><td>Data</td></tr>
     <tr><td>Data</td></tr>
     <tr><td>Data</td></tr>
     <tr><td>Data</td></tr>
   </table>
</div>
<!--/testregion-->
```

The following code will perform this wait:

```C#
// Get the ajaxupdate region.
// Notice how using a testregion simplifies our identification and makes it
// more isolated to the current DOM region being targeted and less prone
// to be affected by other DOM sections.
TestRegion ajaxupdate = ActiveBrowser.Regions["ajaxupdate"];
  
// First wait for the table to show up inside the region. (the first table tag, index=0)
FindParam table = new FindParam("table", 0);
  
// Next wait for the sixth row to be there. 
FindParam sixth_row = new FindParam("tr", 6);
  
// perform the wait for both elements. WaitForElements() takes 1-N FindParam objects to
// to wait for.
ActiveBrowser.Actions.WaitForElements(500, ajaxupdate, false, table, sixth_row);
```
 

```VB
' Get the ajaxupdate region.
' Notice how using a testregion simplifies our identification and makes it
' more isolated to the current DOM region being targeted and less prone
' to be affected by other DOM sections.
Dim ajaxupdate As TestRegion = ActiveBrowser.Regions.Item("ajaxupdate")
  
' First wait for the table to show up inside the region. (the first table tag, index=0)
Dim table As FindParam = New FindParam("table", 0)
  
' Next wait for the sixth row to be there. 
Dim sixth_row As FindParam = New FindParam("tr", 6)
  
' perform the wait for both elements. WaitForElements() takes 1-N FindParam objects to
' to wait for.
ActiveBrowser.Actions.WaitForElements(500, ajaxupdate, False, table, sixth_row)
```

In the above code sample, we used <a href="/code-in-test/advanced-topics-wtc/test-regions-wtc/Introduction" target="_blank">TestRegions</a> to make our automation simpler and targeted at the DOM region we are interested in. If you choose to not use TestRegions, you can simply use the WaitForElement(s) overload that takes in only the FindParam and the Timeout. In that case, all identification will be performed with reference to the root element of the DomTree.
 
You can also use "Chained Identification" to wait for an element. For example if we have a DOM segment that looks like the sample below: 

```HTML
<spanid="myspan">
   <div>
     <table>
       <tr><td>Data</td></tr>
       <tr><td>Data</td></tr>
       <tr><td>Data</td></tr>
       <tr><td>Data</td></tr>
       <tr><td>Data</td></tr>
       <tr><td>Data</td></tr>
     </table>
   </div>
 </span>
```
... and we want to wait until we have six rows available, then we can use chained identification as follows:

```C#
// First find the span by id
FindParam myspan = new FindParam("id=myspan");
  
// Next wait for the sixth row to be there.
FindParam sixth_row = new FindParam("tr", 5);
  
// perform the wait for the row element.
ActiveBrowser.Actions.WaitForElement(new FindParam[] { myspan, sixth_row }, 500);
```
 

```VB
' First find the span by id
Dim myspan As FindParam = New FindParam("id=myspan")
  
' Next wait for the sixth row to be there.
Dim sixth_row As FindParam = New FindParam("tr", 5)
  
' perform the wait for the row element.
ActiveBrowser.Actions.WaitForElement(New FindParam() {myspan, sixth_row}, 500)
```

The above scenario is one of the most common when testing Ajax apps. Therefore, the WaitForElement provides an easy to use overload for these common scenarios where you need to first identify an element by id/name then validate a certain attribute list. This helps reduce the lines of code each time you need to identify an element. If you need a more complex identification, you can use chained identification as described above.

##Retrieving Dynamic Property Values Directly From the DOM##

When using Ajax the application, in most scenarios, updates the document's DOM using JavaScript. The DOM tree provided to your test code by Telerik Testing Framework is automatically updated after each command gets executed against the browser if Browser.AutoDomRefresh property is set to "true," which is the default value. In most scenarios the DOM tree is the latest up-to-date DOM tree from the browser. In cases where the DOM tree is updated without using Telerik browser commands (for example, the page auto-refreshes based on an internal timer, or you are using Pure UI automation), you can always refresh the DOM by calling Browser.RefreshDomTree().
 
In some scenarios that might not even be enough. For example, you want to retrieve a property value that doesn't usually get emitted into the DOM when serialized like the default or inherited values of an unset property or in Firefox the 'value' property of input tags.
 
To help address this issue and potentially other issues, the Telerik infrastructure supports a generic and simple method of retrieving any property of any element directly from the live DOM hosted in the browser. Each Element object in the Telerik Testing Framework has a GetValue<T>() method that you can use to evaluate any custom or standard attribute of your Dom element at any point in your test code or application.
 
For example, if you want to retrieve the text set by a user in an input textbox in Firefox, you can simply do the following:

```C#
// Get the element.
Element input = ActiveBrowser.Find.ById("myinput");
  
// Get its 'value' property from the DOM
string value = input.GetValue<string>("value");
  
// Get its 'display' property from the DOM
string display = input.GetValue<string>("display");
  
// Get its 'visibility' property from the DOM
string visibility = input.GetValue<string>("visibility");
```
 

```VB
' Get the element.
Dim input As Element = ActiveBrowser.Find.ById("myinput")
  
' Get its 'value' property from the DOM
Dim value As String = input.GetValue(Of String)("value")
  
' Get its 'display' property from the DOM
Dim display As String = input.GetValue(Of String)("display")
  
' Get its 'visibility' property from the DOM
Dim visibility As String = input.GetValue(Of String)("visibility")
```

**Note:** If you are retrieving property values of set attributes available in the serialized DOM string, you should use the GetAttribute() method to retrieve these attributes and their values.

##Browser.WaitForAjax()##

This method will wait for any active AJAX requests to complete.

```C#
Manager.ActiveBrowser.WaitForAjax(30000);
```
 

```VB
Manager.ActiveBrowser.WaitForAjax(30000)
```
