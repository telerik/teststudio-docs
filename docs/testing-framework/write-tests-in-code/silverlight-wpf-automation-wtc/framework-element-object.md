---
title: FrameworkElement Object
page_title: FrameworkElement Object
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# FrameworkElement Object

The **FrameworkElement** object is analogous to the <a href="http://msdn.microsoft.com/en-us/library/system.windows.frameworkelement(VS.95).aspx" target="_blank">FrameworkElement</a> in Silverlight and is the base object that all visual elements and controls inherit from in the **ArtOfTest.WebAii.Silverlight.UI** namespace. For customers interested in our extensibility model, the Silverlight Extension does not expose a <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.95).aspx" target="_blank">UIElement</a> and therefore, our **FrameworkElement** can be viewed as the combination of Silverlight's **UIElement + FrameworkElement**.
 
The **FrameworkElement** and all objects that inherit from it get the following infrastructure properties:

<table class="docs">
<tr>
	<th>Property</th><th>Description</th>
</tr>
<tr>
	<td>AbsoluteSiblingTagIndex</td><td>Get the sibling tag index of this FrameworkElement.</td>
</tr>
<tr>
	<td>AbsoluteTagIndex</td><td>Get the absolute index of this XAML tag in the Visual Tree.</td>
</tr>
<tr>
	<td>ActualHeight</td><td>Gets the rendered height of a FrameworkElement.</td>
</tr>
<tr>
	<td>ActualWidth</td><td>Gets the rendered width of a FrameworkElement.</td>
</tr>
<tr>
	<td>Application</td><td>Get the Application object that owns this element.</td>
</tr>
<tr>
	<td>AutomationId</td><td>Gets the AutomationId set on this element if any.</td>
</tr>
<tr>
	<td>Children</td><td>Gets the visual children of this element.</td>
</tr>
<tr>
	<td>Clip</td><td>Gets or sets the <a href="http://msdn.microsoft.com/en-us/library/system.windows.media.geometry(VS.96).aspx" target="_blank">Geometry</a> used to define the outline of the contents of a <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a>.</td>
</tr>
<tr>
	<td>Depth</td><td>Get the depth of this element in the Visual Tree.</td>
</tr>
<tr>
	<td>EnableValidateMouseLocation</td><td>Enables or disables the validation of mouse click locations before performing mouse actions.</td>
</tr>
<tr>
	<td>Find</td><td>Get the Find object used to search the visual children of this element.</td>
</tr>
<tr>
	<td>Height</td><td>Gets or sets the suggested height of a FrameworkElement.</td>
</tr>
<tr>
	<td>HorizontalAlignment</td><td>Gets or sets the horizontal alignment characteristics applied to a FrameworkElement when it is composed within a layout parent, such as a panel or items control.</td>
</tr>
<tr>
	<td>Host</td><td>Returns the SilverlightApp object owning this FrameworkElement.</td>
</tr>
<tr>
	<td>IsHitTestVisible</td><td>Gets or sets whether the contained area of this UIElement can return true values for hit testing.</td>
</tr>
<tr>
	<td>IsTestRegion</td><td>Returns whether or not this FrameworkElement is contained inside a TestRegion (not supported in WebAii 2.0 Beta 2).</td>
</tr>
<tr>
	<td>Language</td><td>Gets or sets localization/globalization language information that applies to a FrameworkElement.</td>
</tr>
<tr>
	<td>Margin</td><td>Gets or sets the outer margin of a FrameworkElement.</td>
</tr>
<tr>
	<td>MaxHeight</td><td>Gets or sets the maximum height constraint of a FrameworkElement.</td>
</tr>
<tr>
	<td>MaxWidth</td><td>Gets or sets the maximum width constraint of a FrameworkElement.</td>
</tr>
<tr>
	<td>MinHeight</td><td>Gets or sets the minimum height constraint of a FrameworkElement.</td>
</tr>
<tr>
	<td>MinWidth</td><td>Gets or sets the minimum width constraint of a FrameworkElement.</td>
</tr>
<tr>
	<td>Name</td><td>Gets (or sets, but see Remarks) the identifying name of the object. The name provides a reference that is initially markup-compiled. After a XAML processor creates the object tree from markup, run-time code can refer to a markup element by this name.</td>
</tr>
<tr>
	<td>Opacity</td><td>Gets or sets the degree of the object's opacity.</td>
</tr>
<tr>
	<td>OpacityMask</td><td>Gets or sets the brush used to alter the opacity of regions of this object.</td>
</tr>
<tr>
	<td>Projection</td><td>Gets or sets the perspective projection (3-D effect) to apply when rendering this <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a>.</td>
</tr>
<tr>
	<td>RenderSize</td><td>Gets the final render size of a <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a>.</td>
</tr>
<tr>
	<td>RenderTransform</td><td>Gets or sets transform information that affects the rendering position of a UIElement.</td>
</tr>
<tr>
	<td>RenderTransformOrigin</td><td>Gets or sets the origin point of any possible render transform declared by <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement.rendertransform(VS.96).aspx" target="_blank">RenderTransform</a>, relative to the bounds of the <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a>.</td>
</tr>
<tr>
	<td>Resources</td><td>Gets the locally defined resource dictionary. In XAML, you can establish resource items as child object elements of the <code>&lt;object.Resources&gt;</code> property element, through XAML implicit collection syntax.</td>
</tr>
<tr>
	<td>Style</td><td>Gets or sets an instance <a href="http://msdn.microsoft.com/en-us/library/system.windows.style(VS.96).aspx" target="_blank">Style</a> that is applied for this object during rendering.</td>
</tr>
<tr>
	<td>TagNameIndex</td><td>Gets the tag name index of the xaml tag name in the visual tree.</td>
</tr>
<tr>
	<td>TechnologyType</td><td>Get the technology type of this element. Always returns TechnologyType.Silverlight for FrameworkElement objects.</td>
</tr>
<tr>
	<td>TextContent</td><td>Gets the text content of this framework element if any.</td>
</tr>
<tr>
	<td>UseLayoutRounding</td><td>Gets or sets a value that determines whether rendering for the object and its subtree should use rounding behavior that aligns rendering to whole pixels.</td>
</tr>
<tr>
	<td>User</td><td>Gets the UI interaction object that allows you to interact with this framework element directly using real mouse and keyboard interactions.</td>
</tr>
<tr>
	<td>VerticalAlignment</td><td>Gets or sets the vertical alignment characteristics applied to a FrameworkElement when it is composed within a parent object such as a panel or items control.</td>
</tr>
<tr>
	<td>Visibility</td><td>Gets or sets the visibility of a <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a>. A <a href="http://msdn.microsoft.com/en-us/library/system.windows.uielement(VS.96).aspx" target="_blank">UIElement</a> that is not visible does not render and does not communicate its desired size to layout.</td>
</tr>
<tr>
	<td>Wait</td><td>Gets a VisualWait object to be used on waiting for Visual elements in the VisualTree.</td>
</tr>
<tr>
	<td>Width</td><td>Gets or sets the width of a FrameworkElement.</td>
</tr>
<tr>
	<td>XamlTag</td><td>Get the XAML tag name of this FrameworkElement. This is used for hierarchy matching and traversal.</td>
</tr>
</table>

## The FrameworkElement Methods

Before describing all of the methods of the FrameworkElement object I'd like to point out the following special features:

1. VisualTree navigation: All FrameworkElements enable you to navigate the visual tree up or down. The object exposes methods and properties like `Parent`, `Children`, `NextSibling`, `PreviousSibling`, `AnySibling<T>`. The navigation also supports control sensitive navigation. For example, if you would like to find the parent 'Grid' that a certain text is contained in you do the following:

	
````C#
WpfApplication app = Manager.ActiveApplication;
Assert.IsNotNull(app);

Grid containerGrid = app.Find.ByText("SomeText").Parent("Grid").As<Grid>();
````

__OR__

If you are working with a custom control that doesn't have a strongly-typed object under **ArtOfTest.WebAii.Silverlight.UI**, the navigation methods all offer a non-generic version that can be used to search for a certain type. For example, let's say you are trying to find the custom control "Bar" that contains some text, then you can do the following:

````C#
WpfApplication app = Manager.ActiveApplication;
Assert.IsNotNull(app);

FrameworkElement barElement = app.Find.ByText("SomeText").Parent("Bar");
````

`Parent`, `NextSibling`, `PreviousSibling` & `AnySibling` all offer a non-generic versions in addition to the generic one.

2. **User Interaction object:**

The FrameworkElement object exposes a user interaction object. The object is exposed as a property named '**User**'. User then exposes all the real automation methods like moving the mouse to click an element, type a text, mouse enter, mouse leave…etc.

**Note:** One of the reasons why we moved these methods into their own object under 'User.xxx' is to help users differentiate between automation that is done by setting/getting properties vs. real automation that used the mouse or keyboard to invoke actions.

3. **Element coordinates:** 


All FrameworkElements offer the ability to get both the relative coordinates of the element within the Silverlight application and the actual coordinates in screen coordinates. The two methods are `GetRectangle()`and `GetScreenRectangle()`.

**Note:** Given that WPF/Silverlight applications allow for rich transforms for visual elements (i.e. rotate, zoom….etc) and some elements like ellipses don't really conform to a rectangle per-say, our coordinate calculations will always return the largest rectangle that contains the actual element with its center right at the center of the element. For example, a GetRectangle on an ellipse will return this:

![SL app][1]

*The highlighting above is using the FrameworkElement.Highlight() method.*

4. **XML Representation**:


Every **FrameworkElement** has a `ToXml()` method on it that returns the VisualTree of that element as an XML formatted string. This is very useful when trying to understand the visual tree at a certain state. [Hint: You can get the entire visual tree of an app by calling `app.VisualTree.Root.ToXml()`]

These are all of the FrameworkElement methods available for use by your automation code:

<table class="docs">
<tr>
	<th>Method</th><th>Description</th>
</tr>
<tr>
	<td>AnySibling(T)</td><td>Return any sibling of this control of type T. The framework first searches for a previous sibling having the specified type. If it finds one that sibling is returned. If it doesn't find one then it searches for the next sibling. If it find one that sibling is returned, otherwise null (Nothing in VB.NET) is returned.</td>
</tr>
<tr>
	<td>As(T)</td><td>Return this framework element as a strongly-typed control of type T.</td>
</tr>
<tr>
	<td>CastAs(T)</td><td>Returns this framework element as a strongly-typed control of type T without enforcing tag name to match the type it is being cast to. This functions gives you free casting abilities between types.</td>
</tr>
<tr>
	<td>Equals</td><td>Determines whether this FrameworkElement is equal to another, by comparing their AutomationReferences.</td>
</tr>
<tr>
	<td>GetChildren</td><td>Get the children of this framework element.</td>
</tr>
<tr>
	<td>GetNextSibling</td><td>Get the next sibling of this FrameworkElement.</td>
</tr>
<tr>
	<td>GetParent</td><td>Get the Parent of this element.</td>
</tr>
<tr>
	<td>GetPrevSibling</td><td>Get the previous sibling.</td>
</tr>
<tr>
	<td>GetRectangle</td><td>Get the bounding rectangle of this FrameworkElement within the owning Silverlight application.</td>
</tr>
<tr>
	<td>GetScreenRectangle</td><td>Return the actual coordinates of this element in absolute screen coordinates taking into account the location of the overall plug-in on the page.</td>
</tr>
<tr>
	<td>Highlight</td><td>Highlight this element in the Silverlight application.</td>
</tr>
<tr>
	<td>NextSibling</td><td>Get the next sibling control of a specific type.</td>
</tr>
<tr>
	<td>Parent</td><td>Get the parent FrameworkElement of this element.</td>
</tr>
<tr>
	<td>PreviousSibling</td><td>Get the previous sibling control of a specific type.</td>
</tr>
<tr>
	<td>Refresh</td><td>Refresh this FrameworkElement within the VisualTree.</td>
</tr>
<tr>
	<td>ScrollToVisible</td><td>Scrolls the web page so that this element is visible in the browser window.</td>
</tr>
<tr>
	<td>ToXml</td><td>Gets an XML formatted string that represents this element and all its children This XML represents the VisualTree.</td>
</tr>
</table>

[1]: /img/testing-framework/write-tests-in-code/silverlight-wpf-automation-wtc/wpf-ui-automation/fig1.png