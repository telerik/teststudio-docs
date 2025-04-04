---
title: Invoking Actions
page_title: Invoking Actions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Invoking Actions on Elements

Once you have found an element you can then interact with it. Many different types of interactions are supported like clicking, mouse hover over, mouse wheel-related actions, keyboard clicks etc.

1.&nbsp; <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Clicking-On-an-Element">Clicking On an Element</a> - invoke a click on a FrameworkElement.

2.&nbsp; <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Sending-Text-to-a-Control">Sending Text to a Control</a> - type text content into a FrameworkElement.

3.&nbsp; <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Mouse-Actions">Mouse Actions</a> - invoking different mouse actions on FrameworkElement.

4.&nbsp; <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Framework-Element-Properties-and-Actions">Framework Element Properties and Actions.</a>
	* <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#UI-Element-Actions">UI Element Actions</a> - understanding wrappers.
	* <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Telerik-Testing-Framework-Specific-Properties">Telerik Testing Framework Specific Properties</a> - commonly used Properties of Telerik's FrameworkElement.
	* <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Telerik-Testing-Framework-Specific-Methods">Telerik Testing Framework Specific Methods</a> - commonly used Methods of Telerik's FrameworkElement.
	* <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Getting-and-Setting-Properties-on-Elements">Getting and Setting Properties on Elements</a> - working with non-built in Properties.
5. <a href="/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/invoking-actions#Invoking-Element-Methods">Invoking Element Methods</a> - invoke any method attached to an element.

## Clicking On an Element

To invoke a UI action, use the User object that is attached to every UI element. For example, to click on an element such as a button, enter code like this:

````C#
//In this example app can be a Silverlight application or the MainWindow element of a WPF application 
// Click the ShowGuide button.
app.Find.ByName("guideButton").User.Click();
 
// Right click the ShowGuide button 5 pixels away from the center of the control
app.Find.ByName("guideButton").User.Click(MouseClickType.RightClick,
     new System.Drawing.Point(5, 5), OffsetReference.AbsoluteCenter);
````
````VB
'In this example app can be a Silverlight application or the MainWindow of a WPF application 
' Click the ShowGuide button.
app.Find.ByName("guideButton").User.Click()
 
' Right click the ShowGuide button 5 pixels away from the center of the control
app.Find.ByName("guideButton").User.Click(MouseClickType.RightClick, _
                                       New System.Drawing.Point(5, 5), _
                                        OffsetReference.AbsoluteCenter)
````

## Sending Text to a Control

To send text to the control use one of the following lines of code:

````C#
searchText.User.TypeText("Abe Lincoln", 100);
 
searchText.User.KeyPress(System.Windows.Forms.Keys.L, 100);
 
searchText.User.KeyDown(System.Windows.Forms.Keys.L);
searchText.User.KeyUp(System.Windows.Forms.Keys.L);
````
````VB
searchText.User.TypeText("Abe Lincoln", 100)
 
searchText.User.KeyPress(Windows.Forms.Keys.L, 100)
 
searchText.User.KeyDown(Windows.Forms.Keys.L)
searchText.User.KeyUp(Windows.Forms.Keys.L)
````

## Mouse Actions

To perform one of the various possible mouse actions use one of the following lines of code:

````C#
admin2.Find.ByType("Thumb").User.DragTo(admin3.Find.ByType("Thumb"));
admin1.User.HoverOver();
admin1.User.MouseEnter(OffsetReference.LeftCenter);
admin1.User.MouseLeave(OffsetReference.RightCenter);
admin1.User.TurnMouseWheel(5, MouseWheelTurnDirection.Backward, false);
````
````VB
admin2.Find.ByType("Thumb").User.DragTo(admin3.Find.ByType("Thumb"))
admin1.User.HoverOver()
admin1.User.MouseEnter(OffsetReference.LeftCenter)
admin1.User.MouseLeave(OffsetReference.RightCenter)
admin1.User.TurnMouseWheel(5, MouseWheelTurnDirection.Backward, False)
````

## Framework Element Properties and Actions

All of the Telerik Testing Framework UI controls derive from the FrameworkElement object. Our FrameworkElement object mirrors as closely as possible XAML's FrameworkElement as defined in MSDN <a href="http://msdn.microsoft.com/en-us/library/system.windows.frameworkelement%28VS.96%29.aspx" target="_blank">here</a>. For customers interested in our extensibility model, the Silverlight Extension does not expose a <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a> and therefore, our FrameworkElement can be viewed as the combination of Silverlight/WPF's UIElement + FrameworkElement. These are just few examples of the many available properties of our FrameworkElement object:

<table class="docs">
<tr>
	<th>Property</th><th>Description</th>
</tr>
<tr>
	<td>AutomationId</td><td>Retrieves the Automation ID assigned to this element.</td>
</tr>
<tr>
	<td>Children</td>Retrieves a list of elements that are children of this element in the visual tree.</td>
</tr>
<tr>
	<td>Clip</td><td>Gets or sets the Geometry used to define the outline of the contents of a UI Element.</td>
</tr>
<tr>
	<td>Height</td><td>Gets or sets the suggested height of a FrameworkElement.</td>
</tr>
<tr>
	<td>Opacity</td><td>Gets or sets the degree of the object's opacity.</td>
</tr>
<tr>
	<td>OpacityMask</td><td>Gets or sets the brush used to alter the opacity of regions of this object.</td>
</tr>
<tr>
	<td>Width</td><td>Gets or sets the suggested width of a FrameworkElement.</td>
</tr>
</table>

## UI Element Actions

Each UI element wrapper class contained in Telerik Testing Framework has a set of properties used to access the properties appropriate for that UI element. For example: The Calendar control has a SelectedDate property that you can use to read and/or set the currently selected date of the control. It also has a SelectionMode property you can use to read and/or change the selection mode from a single date to a multi-range date selection. The CheckBox control has an IsChecked property you can use to read/set the checked state of the control and so on.

## Telerik Testing Framework Specific Properties

We have implemented a few special properties in our FrameworkElement object to aid in automation. These include:

<table class="docs">
<tr>
	<th>Property</th><th>Description</th>
</tr>
<tr>
	<td>AbsoluteSiblingTagIndex</td><td>Returns the sibling tag index of this FrameworkElement relative to its other siblings within the Visual Tree.</td>
</tr>
<tr>
	<td>AbsoluteTagIndex</td><td>Returns the absolute index of this XAML tag within the entire Visual Tree.</td>
</tr>
<tr>
	<td>Application</td><td>Gets the Application object that owns this element.</td>
</tr>
<tr>
	<td>EnableValidateMouseLocation</td><td>Enables or disables the validation of mouse click locations before performing mouse actions.</td>
</tr>
<tr>
	<td>Find</td><td>Gets the Find object that can be used to search the visual children of this element.</td>
</tr>
<tr>
	<td>TagNameIndex</td><td>Gets the tag name index of the XAML tag name in the visual tree.</td>
</tr>
<tr>
	<td>User</td><td>Gets the UI interaction object which allows you to interact with this framework element directly using real mouse and keyboard interactions.</td>
</tr>
<tr>
	<td>Wait</td><td>Gets a VisualWait object you can use to wait for Visual elements in the Visual Tree.</td>
</tr>
<tr>
	<td>XamlTag</td><td>Gets the XAML tag name of this FrameworkElement. This is used for hierarchy matching and traversal.</td>
</tr>
</table>

## Telerik Testing Framework Specific Methods

The FrameworkElement class implements a number of methods just for purpose of test automation. Some of the most commonly used include:

<table class="docs">
<tr>
	<th>Property</th><th>Description</th>
</tr>
<tr>
	<td><code>CastAs&lt;T&gt;()</code></td><td>Returns a FrameworkElement as a strongly-typed control. Does not enforce a tagname to match the type.</td>
</tr>
<tr>
	<td><code>&lt;GetChildren()&gt;</code></td>Returns the child elements of the FrameworkElement.</td>
</tr>
<tr>
	<td><code>&lt;GetNextSibling()&gt;</code></td><td>Returns the next sibling of  the FrameworkElement.</td>
</tr>
<tr>
	<td><code>&lt;Parent()&gt;</code></td><td>Returns the parent element of the current Framework Element</td>
</tr>
<tr>
	<td><code>&lt;ScrollToVisible()&gt;</code></td><td>Scrolls the browser so that the Framework Element is visible.</td>
</tr>
</table>

## Getting and Setting Properties on Elements

If the property of an element you want to get or set isn't available as a property in the UI element wrapper object, you can use the GetProperty and SetProperty from the FrameworkElement object to get/set it. This is especially useful if you start designing your own custom Silverlight UI controls or use a third party custom control. Let's suppose I have a UI element that represents an airline ticket. One of the many obvious properties such a control would need to have is flight number. To fetch this property from the control I can use code like this:

````C#
// Fetch the flight number from the ticket
FrameworkElement ticket = app.FindName("airlineTicket");
AutomationProperty flightNoProperty = new AutomationProperty("flightNo", typeof(string));
string flightNo = (string)ticket.GetProperty(flightNoProperty);
 
// Update the flight number on the ticket
ticket.SetProperty(flightNoProperty, "HX-1572");
````
````VB
' Fetch the flight number from the ticket
Dim ticket As FrameworkElement = app.FindName("airlineTicket")
Dim flightNoProperty As New AutomationProperty("flightNo", GetType(String))
Dim flightNo As String = DirectCast(ticket.GetProperty(flightNoProperty), String)
 
' Update the flight number on the ticket
ticket.SetProperty(flightNoProperty, "HX-1572")
````

## Invoking Element Methods

Another advanced feature of the framework is the ability to invoke any method attached to an element. Here's how to invoke the ScrollToVerticalOffset method of a ScrollViewer element.

````C#
ScrollViewer searchScroll = app.FindName("patientSearchScroller").Find.ByType<ScrollViewer>();
searchScroll = app.FindName().Find.ByType<>();
 
AutomationMethod scrollVert = new AutomationMethod("ScrollToVerticalOffset", null);
searchScroll.InvokeMethod(scrollVert, 2000);
````
````VB
Dim searchScroll As ScrollViewer = app.FindName("patientSearchScroller").Find.ByType(Of ScrollViewer)()
 
Dim scrollVert As New AutomationMethod("ScrollToVerticalOffset", Nothing)
searchScroll.InvokeMethod(scrollVert, 2000)
````