---
title: Hybrid
page_title: Hybrid
description: "Telerik Mobile Testing - API Reference - Hybrid"
position: 5
publish: true
slug: ms-hybrid-api
---

# Hybrid

Methods
<select id="methodsSelect" onchange="window.location.hash='#'+event.currentTarget.selectedOptions[0].value;">
<option value="click">Click</option>
<option value="doubleclick">DoubleClick</option>
<option value="drag">Drag</option>
<option value="dragtodisplacement">DragToDisplacement</option>
<option value="dragtoelement">DragToElement</option>
<option value="dragtopoint">DragToPoint</option>
<option value="executescript">ExecuteScript</option>
<option value="getattribute">GetAttribute</option>
<option value="getchecked">GetChecked</option>
<option value="getcolumncount">GetColumnCount</option>
<option value="gethtml">GetHtml</option>
<option value="getinerror">GetInError</option>
<option value="getpaused">GetPaused</option>
<option value="getrowcount">GetRowCount</option>
<option value="getscriptresult">GetScriptResult</option>
<option value="getselectedindex">GetSelectedIndex</option>
<option value="getselectedtext">GetSelectedText</option>
<option value="getselectedvalue">GetSelectedValue</option>
<option value="getstyle">GetStyle</option>
<option value="gettextcontent">GetTextContent</option>
<option value="getvalue">GetValue</option>
<option value="hoverover">HoverOver</option>
<option value="pinchin">PinchIn</option>
<option value="pinchout">PinchOut</option>
<option value="presskey">PressKey</option>
<option value="rightclick">RightClick</option>
<option value="scroll">Scroll</option>
<option value="scrolltoelement">ScrollToElement</option>
<option value="setattribute">SetAttribute</option>
<option value="setchecked">SetChecked</option>
<option value="sethtml">SetHtml</option>
<option value="setpaused">SetPaused</option>
<option value="setselectedindex">SetSelectedIndex</option>
<option value="setselectedtext">SetSelectedText</option>
<option value="setselectedvalue">SetSelectedValue</option>
<option value="setstyle">SetStyle</option>
<option value="settextcontent">SetTextContent</option>
<option value="setvalue">SetValue</option>
<option value="swipe">Swipe</option>
<option value="tap">Tap</option>
<option value="tapandhold">TapAndHold</option>
<option value="tapatlocation">TapAtLocation</option>
<option value="tapatpoint">TapAtPoint</option>
<option value="tapcenterleft">TapCenterLeft</option>
<option value="tapcenterright">TapCenterRight</option>
<option value="twofingerrotate">TwoFingerRotate</option>
<option value="wait">Wait</option>
<option value="waitfor">WaitFor</option>
<option value="waitforscriptresult">WaitForScriptResult</option>
</select>

Methods for automating hybrid applications.

Since hybrid app is a web app running inside a native container (WebView), hybrid API methods that target specific element accept a web query to identify the element. If the app contains only one native container (WebView), using a API overload method that accepts a WebQuery object to identify that element suffices. However, if the app implements more than one native containers (WebView), finding an element inside the different native containers requires using and API overload method that identifies the native container first in which the web element is located. Bellow you can find an example of 2 overloads of the Tap hybrid API method:

```C#
// This will perform a web tap action on the provided element located inside the first found WebView object in the app.
this.ActiveDevice.Web.Tap(this.Elements.MyScreen.webview.BUTTON);

// This will perform a web tap action on the provided element located inside a specific WebView object in the app.
this.ActiveDevice.Web.Tap(this.Elements.MyScreen.webview.View, this.Elements.MyScreen.webview.BUTTON);
```

```VB
' Me.ActiveDevice.Web.Tap(Elements.MyScreen.webview.BUTTON)

' Me.ActiveDevice.Web.Tap(Elements.MyScreen.webview.View, Elements.MyScreen.webview.BUTTON)
```

 > For brevity, API methods in this topic are listed with their WebView/Element overloads. However, based on the actual scenario to be tested any of the other available overloads can be used instead.

##Methods

<a id="click"></a>
## Click(Query[] viewQuery, Query[] elementQuery)

Perform a click on an element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// This will perform a click action on the provided web element
this.ActiveDevice.Web.Click(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.Click(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="doubleclick"></a>
## DoubleClick(Query[] viewQuery, Query[] elementQuery)

Perform a double click on an element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// This will perform a double-click on the provided web element
this.ActiveDevice.Web.DoubleClick(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.DoubleClick(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="drag"></a>
## Drag(Query[] viewQuery, Query[] elementQuery, int offsetX, int offsetY)

Drag an element to a specific point.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*offsetX (int)* - Destination point horizontal offset from element center.

*offsetY (int)* - Destination point vertical offset from element center.

### Example

```C#
// This will drag a draggable web element to 100x,300y point realtive to the center of the provided element
this.ActiveDevice.Web.Drag(Elements.MyScreen.WebView.Drag, 100,300);
```

```VB
Me.ActiveDevice.Web.Drag(Elements.MyScreen.WebView.Drag, 100, 300)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtodisplacement"></a>
## DragToDisplacement(Query[] viewQuery, Query[] elementQuery, TapPoint fromPoint, TapPoint displacement, int steps)

Performs drag gesture on element specified by the query to a displacement point from that element

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*fromPoint (TapPiont)* - Starting point of drag gesture. If null, defaults to center point of element.

*displacement (TapPiont)* - Displacement, represented as point object. If null, defaults to center point of element.

*steps (int)* - The amount of touches to generate to complete the drag gesture.  Valid values are in the range: 3 - 1000.

### Example

```C#
// This will drag an element in web view from 0x, 0y point (relative to the element) to 100x, 300y point relative to the first TapPoint(0,0) in 150 simulated touches
this.ActiveDevice.Web.DragToDisplacement(Elements.MyScreen.WebView.DragElement, new TapPoint(0,0), new TapPoint(100,300), 150);
```

```VB
Me.ActiveDevice.Web.DragToDisplacement(Elements.MyScreen.WebView.DragElement, New TapPoint(0, 0), New TapPoint(100, 300), 150)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtoelement"></a>
## DragToElement(Query[] viewQuery, Query[] dragElementQuery, Query[] toElementQuery)

Drag an element over another element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*dragElementQuery (WebQuery)* - WebQuery object that identifies element to be dragged. The element to be dragged must be draggable.

*toElementQuery (WebQuery)* - WebQuery object that identifies element the dragged element will be dragged over.

### Example

```C#
// Drag element `DragElement` on top of element `TestField`
this.ActiveDevice.Web.DragToElement(Elements.MyScreen.WebView.DragElement, Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.DragToElement(Elements.MyScreen.WebView.DragElement, Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtopoint"></a>
## DragToPoint(Query[] viewQuery, Query[] elementQuery, TapPoint fromPoint, TapPoint toPoint, int steps )

Drag an element to a specified point.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*fromPoint (TapPiont)* - Starting point of drag gesture. If null, defaults to center point of element.

*displacement (TapPiont)* - Finishing point of drag gesture. If null, defaults to center point of element.

*steps (int)* - The amount of touches to generate to complete the drag gesture.  Valid values are in the range: 3 - 1000.

### Example

```C#
// This will drag an element in web view from 0x, 0y point inside the specified element to 100x, 300y point relative to the element in 150 simulated touches
this.ActiveDevice.Web.DragToPoint(Elements.MyScreen.WebView.DragElement, new TapPoint(0,0), new TapPoint(100,300), 150);
```

```VB
Me.ActiveDevice.Web.DragToPoint(Elements.MyScreen.WebView.DragElement, New TapPoint(0, 0), New TapPoint(100, 300), 150)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="executescript"></a>
## ExecuteScript(Query[] viewQuery, string script, Query[] elementQuery)

Execute a script into a web view.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*script (string)* - String that is transferred to application under test and evaled into current web view.

*elementQuery (WebQuery)* - WebQuery for target element. Element defined by this parameter can be accessed using `targetElement` variable inside the script parameter string.

### Example

```C#
// Executes the script of the string parameter on the web view under test. Deprecated: Use getScriptResult instead.
this.ActiveDevice.Web.ExecuteScript("document.getElementsByTagName(\"div\")");
```

```VB
Me.ActiveDevice.Web.ExecuteScript("document.getElementsByTagName(""div"")")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getattribute"></a>
## GetAttribute(Query[] viewQuery, Query[] elementQuery, string attrName)

Get attribute value of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*attrName (string)* - Name of the attribute.

### Return Value

A string containing the value of the specified attribute.

### Example

```C#
// Get the `id` attribute value of `DragElement` as string
string idAttribute = this.ActiveDevice.Web.GetAttribute(Elements.MyScreen.WebView.DragElement, "id");
```

```VB
Dim idAttribute As String = Me.ActiveDevice.Web.GetAttribute(Elements.MyScreen.WebView.DragElement, "id")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getchecked"></a>
## GetChecked(Query[] viewQuery, Query[] elementQuery)

Gets checked state of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

A bool containing the checked state of specific element.

### Example

```C#
// Returns the checked state of the checkBox as boolean
bool state = this.ActiveDevice.Web.GetChecked(Elements.MyScreen.WebView.CheckBox);
```

```VB
Dim state As Boolean = Me.ActiveDevice.Web.GetChecked(Elements.MyScreen.WebView.CheckBox)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>


<a id="getcolumncount"></a>
## GetColumnCount(Query[] viewQuery, Query[] elementQuery, uint rowIndex)

Get the number of cells of a specific row in a table.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*rowIndex (unit)* - Index of row which cells count is needed.

### Return Value

The number of cells in a particular row in a table element.

### Example

```C#
// Returns the number of columns in the specified table row.
uint count = this.ActiveDevice.Web.GetColumnCount(Elements.MyScreen.WebView.TableView, 1);
```

```VB
Dim count As UInteger = Me.ActiveDevice.Web.GetColumnCount(Elements.MyScreen.WebView.TableView, 1)
```
<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="gethtml"></a>
## GetHtml(Query[] viewQuery, Query[] elementQuery)

Get inner html of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

A string containing the inner html of the specified element.

### Example

```C#
// Gets the inner HTML of CheckBox
string html = this.ActiveDevice.Web.GetHtml(Elements.MyScreen.WebView.CheckBox);
```

```VB
Dim html As String = Me.ActiveDevice.Web.GetHtml(Elements.MyScreen.WebView.CheckBox)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getinerror"></a>
## GetInError(Query[] viewQuery, Query[] elementQuery)

Gets error state of audio/video element. This function returns inconsistent results for mobile browsers.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

True if control is in error state, otherwise false.

### Example

```C#
bool statePlayer = this.ActiveDevice.Web.GetInError(Elements.MyScreen.WebView.Player);
```

```VB
Dim statePlayer As Boolean = Me.ActiveDevice.Web.GetInError(Elements.MyScreen.WebView.Player)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getpaused"></a>
## GetPaused(Query[] viewQuery, Query[] elementQuery)

Get paused state of audio/video element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

True if audio/video element is paused, otherwise false.

### Example

```C#
// Get the paused state of a `video` element.
bool statePaused = this.ActiveDevice.Web.GetPaused(Elements.MyScreen.WebView.Player);
```

```VB
Dim statePaused As Boolean = Me.ActiveDevice.Web.GetPaused(Elements.MyScreen.WebView.Player)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getrowcount"></a>
## GetRowCount(Query[] viewQuery, Query[] elementQuery)

Get number of rows of a table element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

The number of rows of a table element.

### Example

```C#
// Returns the number of rows in the TableView
uint rowCount = this.ActiveDevice.Web.GetRowCount(Elements.MyScreen.WebView.TableView);
```

```VB
Dim rowCount As UInteger = Me.ActiveDevice.Web.GetRowCount(Elements.MyScreen.WebView.TableView)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getscriptresult"></a>
## GetScriptResult(Query[] viewQuery, string script, Query[] elementQuery)

Executes a script into a web view and returns the result.

**Note:** In order to use this method you should add a reference assembly to **Microsoft.CSharp.dll** and **System.Core.dll** from the [project settings]({% slug ms-project-settings%}#References).

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*script (string)* - String that is transferred and evaled into current web view.

*elementQuery (WebQuery)* - WebQuery for target element. Element defined by this parameter can be accessed using `targetElement` variable inside the script parameter string.

### Example

```C#
// This will execute the script of the string parameter and save value of the element id property as object.
object result = this.ActiveDevice.Web.GetScriptResult("document.getElementsByTagName(\"div\").id");
```

```VB
Dim result As Object = Me.ActiveDevice.Web.GetScriptResult("document.getElementsByTagName(""div"").id")
```

### Return Value

Result of script execution.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedindex"></a>
## GetSelectedIndex(Query[] viewQuery, Query[] elementQuery)

Get selected index of a select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

Array of numbers containing the selected indexes.

### Example

```C#
// Get the selected index of the `Select` element (multiple items can be selected)
uint[] index = this.ActiveDevice.Web.GetSelectedIndex(Elements.MyScreen.WebView.Select);
```

```VB
Dim index As UInteger() = Me.ActiveDevice.Web.GetSelectedIndex(Elements.MyScreen.WebView.Select)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedtext"></a>
## GetSelectedText(Query[] viewQuery, Query[] elementQuery)

Get selected text values of select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

Array of strings containing the selected text(s).

### Example

```C#
// Get the selected text of the `Select` element (multiple items can be selected)
string[] selectedText = this.ActiveDevice.Web.GetSelectedText(Elements.MyScreen.WebView.Select);
```

```VB
Dim selectedText() As String = Me.ActiveDevice.Web.GetSelectedText(Elements.MyScreen.WebView.Select)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedvalue"></a>
## GetSelectedValue(Query[] viewQuery, Query[] elementQuery)

Get selected value strings of select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

Array of strings containing the selected value(s).

### Example

```C#
// Get the selected value of the `Select` element (multiple items can be selected)
string[] selectedValue = this.ActiveDevice.Web.GetSelectedValue(Elements.MyScreen.WebView.Select);
```

```VB
Dim selectedValue As String() = Me.ActiveDevice.Web.GetSelectedValue(Elements.MyScreen.WebView.Select)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getstyle"></a>
## GetStyle(Query[] viewQuery, Query[] elementQuery, string styleProp)

Get the value of a specific style property.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*styleProp (string)* - Name of the style attribute.

### Return Value

The value of requested style property.

### Example

```C#
// Get the width value.
string style = this.ActiveDevice.Web.GetStyle(Elements.MyScreen.WebView.TestField, "width");
```

```VB
Dim style As String = Me.ActiveDevice.Web.GetStyle(Elements.MyScreen.WebView.TestField, "width")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="gettextcontent"></a>
## GetTextContent(Query[] viewQuery, Query[] elementQuery)

Get text content of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

A string containing the text content value.

### Example

```C#
// This will return the text content of the test element
string textContent = this.ActiveDevice.Web.GetTextContent(Elements.MyScreen.WebView.TestField);
```

```VB
Dim textContent As String = Me.ActiveDevice.Web.GetTextContent(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getvalue"></a>
## GetValue(Query[] viewQuery, Query[] elementQuery)

Get value of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Return Value

A string containing the value of the specified element.

### Example

```C#
// This will return the value of the test element
string valueOfElement = this.ActiveDevice.Web.GetValue(Elements.MyScreen.WebView.TestField);
```

```VB
Dim valueOfElement As String = Me.ActiveDevice.Web.GetValue(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="hoverover"></a>
## HoverOver(Query[] viewQuery, Query[] elementQuery)

Perform a mouse hover over a web element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// Perform a mouse hover action
this.ActiveDevice.Web.HoverOver(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.HoverOver(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>


<a id="pinchin"></a>
## PinchIn(Query[] viewQuery, Query[] elementQuery, TapPoint point, int distance, int steps)

Perform pinch in gesture at the specified location within the element specified by the query. 

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*point (TapPoint)* - Coordintes of pinch center point. If null, defaults to center point of element.

*distance (int)* - Distance away from the center to start. Minimum value is 20.

*steps (int)* - The amount of touches to generate to complete the pinch. Valid values are in the range: 3 - 1000.

### Example

```C#
// Perform a pinch in over the test element where the pinch will start at 100x, 100y point within the element and will pinchIn 20px in 50 simulated touches
this.ActiveDevice.Web.PinchIn(Elements.MyScreen.WebView.TestField, new TapPoint(100,100), 20, 50);
```

```VB
Me.ActiveDevice.Web.PinchIn(Elements.MyScreen.WebView.TestField, New TapPoint(100, 100), 20, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pinchout"></a>
## PinchOut(Query[] viewQuery, Query[] elementQuery, TapPoint point, int distance, int steps)

Perform pinch out gesture at the specified location within the element specified by the query.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*point (TapPoint)* - Coordintes of pinch center point. If null, defaults to center point of element.

*distance (int)* - Distance away from the center to start. Minimum value is 20.

*steps (int)* - The amount of touches to generate to complete the pinch. Valid values are in the range: 3 - 1000.

### Example

```C#
// Perform a pinch out over the test element where the pinch out will start at 100x,100y point within the element and will pinchOut 20px in 50 simulated touches
this.ActiveDevice.Web.PinchOut(Elements.MyScreen.WebView.TestField, new TapPoint(100,100), 20, 50);
```

```VB
Me.ActiveDevice.Web.PinchOut(Elements.MyScreen.WebView.TestField, New TapPoint(100, 100), 20, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="presskey"></a>
## PressKey(Query[] viewQuery, Query[] elementQuery, int keyCode, bool alt, bool ctrl, bool shift)

Invoke press key event on specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*keyCode (int)* - Code of the key.

*alt (boolean)* - Boolean value indicating whether ALT is pressed. The default is false.

*ctrl (boolean)* - Boolean value indicating whether CTRL is pressed. The default is false.

*shift (boolean)* - Boolean value indicating whether SHIFT is pressed. The default is false.

### Example

```C#
// This will invoke the press CAPS LOCK key event (with code 20) over the test element 
this.ActiveDevice.Web.PressKey(Elements.MyScreen.WebView.TestField, 20);
```

```VB
Me.ActiveDevice.Web.PressKey(Elements.MyScreen.WebView.TestField, 20)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="rightclick"></a>
## RightClick(Query[] viewQuery, Query[] elementQuery)

Perform a right click on an element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Perform a right click on the test element
this.ActiveDevice.Web.RightClick(Elements.MyScreen.WebQuery.TestField);
```

```VB
Me.ActiveDevice.Web.RightClick(Elements.MyScreen.WebQuery.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="scroll"></a>
## Scroll(Query[] viewQuery, Query[] elementQuery, int x = 0, int y = 0)

Scroll the web view to any element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*x (int)* - The X confidantes of the specific element.

*y (int)* - The Y confidantes of the specific element.

### Example

```C#
// Scroll to a 300x, 300y point relative to the element
this.ActiveDevice.Web.Scroll(Elements.MyScreen.WebView.TestField, 300, 300);
```

```VB
Me.ActiveDevice.Web.Scroll(Elements.MyScreen.WebView.TestField, 300, 300)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="scrolltoelement"></a>
## ScrollToElement(Query[] viewQuery, Query[] elementQuery)

Scroll the web page to any element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// Scroll to the test element to make it visible on the screen
this.ActiveDevice.Web.ScrollToElement(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.ScrollToElement(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setattribute"></a>
## SetAttribute(Query[] viewQuery, Query[] elementQuery, string attrName, string attrValue)

Set attribute of specific element to a specific value.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*attrName (string)* - Name of the attribute.

*attrValue (string)* - Value to be set.

### Example

```C#
// Set the id attribute of the test element to test
this.ActiveDevice.Web.SetAttribute(Elements.MyScreen.WebView.TestField, "id", "test");
```

```VB
Me.ActiveDevice.Web.SetAttribute(Elements.MyScreen.WebView.TestField, "id", "test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setchecked"></a>
## SetChecked(Query[] viewQuery, Query[] elementQuery, bool checkedValue)

Sets checked state of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - Query object that identifies an element uniquely.

*checkedValue (boolean)* - Checked state value to be set.

### Example

```C#
// Set the state of the checklbox to false
this.ActiveDevice.Web.SetChecked(Elements.MyScreen.WebView.CheckBox, false);
```

```VB
Me.ActiveDevice.Web.SetChecked(Elements.MyScreen.WebView.CheckBox, False)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="sethtml"></a>
## SetHtml(Query[] viewQuery, Query[] elementQuery, string html)

Set inner html of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*html (sting)* - The Html that will be inserted in the specific element.

### Example

```C#
// Set the '<label>text<label>' html to the test element
this.ActiveDevice.Web.SetHtml(Elements.MyScreen.WebView.TestField, "<label>text<label>");
```

```VB
Me.ActiveDevice.Web.SetHtml(Elements.MyScreen.WebView.TestField, "<label>text<label>")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setpaused"></a>
## SetPaused(Query[] viewQuery, Query[] elementQuery, bool pausedState)

Set paused state of audio/video element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*pausedState (boolean)* - Paused state to be set.

### Example

```C#
// This method will pause the video player
this.ActiveDevice.Web.SetPaused(Elements.MyScreen.WebView.Player, true);
```

```VB
Me.ActiveDevice.Web.SetPaused(Elements.MyScreen.WebView.Player, True)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedindex"></a>
## SetSelectedIndex(Query[] viewQuery, Query[] elementQuery, params uint[] indexes)

Set selected index of a select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*indexes (uint array)* - Array of indexes to be selected.

### Example

```C#
// Selects index 3 from the `select` element
this.ActiveDevice.Web.SetSelectedIndex(Elements.MyScreen.WebView.Select, 3);
```

```VB
Me.ActiveDevice.Web.SetSelectedIndex(Elements.MyScreen.WebView.Select, 3)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedtext"></a>
## SetSelectedText(Query[] viewQuery, Query[] elementQuery, params string[] text)

Set selected text of a select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - Query object that identifies an element uniquely.

*text (string array)* - Array of strings to be selected.

### Example

```C#
// Selects a specific item by its text in a `select` element
this.ActiveDevice.Web.SetSelectedText(Elements.MyScreen.WebView.Select, "text1");
```

```VB
Me.ActiveDevice.Web.SetSelectedText(Elements.MyScreen.WebView.Select, "text1")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedvalue"></a>
## SetSelectedValue(Query[] viewQuery, Query[] elementQuery, params string[] values)

Set selected value of a select element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*values (string array)* - Array of strings to be selected.

### Example

```C#
// Selects a specific item by its value in a `select` element
this.ActiveDevice.Web.SetSelectedValue(Elements.MyScreen.WebView.Select, "value2");
```

```VB
Me.ActiveDevice.Web.SetSelectedValue(Elements.MyScreen.WebView.Select, "value2")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setstyle"></a>
## SetStyle(Query[] viewQuery, Query[] elementQuery, string styleProp, string styleValue)

Set specific style property value.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*styleProp (string)* - Name of the style attribute.

*styleValue (string)* - Value to be set.

### Example

```C#
// This will set the width of the testElement to 50 px
this.ActiveDevice.Web.SetStyle(Elements.MyScreen.WebView.TestField, "width", "50px");
```

```VB
Me.ActiveDevice.Web.SetStyle(Elements.MyScreen.WebView.TestField, "width", "50px")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="settextcontent"></a>
## SetTextContent(Query[] viewQuery, Query[] elementQuery, string textContent)

Set text content of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*textContent (string)* - Text content to be set.

### Example

```C#
// This will set the text content of the test element
this.ActiveDevice.Web.SetTextContent(Elements.MyScreen.WebView.TestField, "textToSet");
```

```VB
Me.ActiveDevice.Web.SetTextContent(Elements.MyScreen.WebView.TestField, "textToSet")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setvalue"></a>
## SetValue(Query[] viewQuery, Query[] elementQuery, string value)

Set value of specific element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - Query object that identifies an element uniquely.

*value (string)* - Value to be set.

### Example

```C#
// Set "test" value to the test element
this.ActiveDevice.Web.SetValue(Elements.MyScreen.WebView.TestField, "test");
```

```VB
Me.ActiveDevice.Web.SetValue(Elements.MyScreen.WebView.TestField, "test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="swipe"></a>
## Swipe(Query[] viewQuery, Query[] elementQuery, SwipeDirection direction, int swipeDistance)

Perform a swipe gesture across the element specified by the query. 

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*direction (SwipeDirection)* - Direction to swipe.

*swipeDistance (int)* - Swipe distance, default is '200'.

### Example

```C#
// Swipe right on the test element
this.ActiveDevice.Web.Swipe(Elements.MyScreen.WebView.TestField, SwipeDirection.Right);
```

```VB
Me.ActiveDevice.Web.Swipe(Elements.MyScreen.WebView.TestField, SwipeDirection.Right)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tap"></a>
## Tap(Query[] viewQuery, Query[] elementQuery, int tapCount, int tapDownDelay, int tapUpDelay)

Tap a web element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

*tapDownDelay (int)* - Tap down delay in miliseconds. Min value 50.

*tapUpDelay (int)* - Tap up delay in miliseconds. Min value 50.

### Example

```C#
// Tap action on the test element
this.ActiveDevice.Web.Tap(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.Tap(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapandhold"></a>
## TapAndHold(Query[] viewQuery, Query[] elementQuery)

Perform tap-and-hold gesture at the center of the element.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// Tap and hold action on the center of the test element
this.ActiveDevice.Web.TapAndHold(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.TapAndHold(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatlocation"></a>
## TapAtLocation(Query[] viewQuery, Query[] elementQuery, int X, int Y, int tapCount)

Tap an element on particular location. 

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*X (int)* - X coordinate of point to be tapped.

*Y (int)* - Y coordinate of point to be tapped.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

### Example

```C#
// Tap at 50x, 50y point within the test element
this.ActiveDevice.Web.TapAtLocation(Elements.MyScreen.WebView.TestField, 50, 50, 1);
```

```VB
Me.ActiveDevice.Web.TapAtLocation(Elements.MyScreen.WebView.TestField, 50, 50, 1)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatpoint"></a>
## TapAtPoint(Query[] viewQuery, Query[] elementQuery, TapPoint point, int tapCount, int tapDownDelay, int tapUpDelay)

Tap an element on particular point. 

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*point (TapPoint)* - Point inside element to be tapped.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

*tapDownDelay (int)* - Tap down delay in miliseconds. Min value 50.

*tapUpDelay (int)* - Tap up delay in miliseconds. Min value 50.

### Example

```C#
// Tap at 50x, 50y point within the test element
this.ActiveDevice.Web.TapAtPoint(Elements.MyScreen.WebView.TestField, new TapPoint(50,50));
```

```VB
Me.ActiveDevice.Web.TapAtPoint(Elements.MyScreen.WebView.TestField, New TapPoint(50, 50))
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterleft"></a>
## TapCenterLeftQuery[] viewQuery, Query[] elementQuery)

Tap an element on center left point.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// Tap an element on center left point.
this.ActiveDevice.Web.TapCenterLeft(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.TapCenterLeft(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterright"></a>
## TapCenterRight(Query[] viewQuery, Query[] elementQuery)

Tap an element on center right point.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

### Example

```C#
// Tap an element on center right point.
this.ActiveDevice.Web.TapCenterRight(Elements.MyScreen.WebView.TestField);
```

```VB
Me.ActiveDevice.Web.TapCenterRight(Elements.MyScreen.WebView.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="twofingerrotate"></a>
## TwoFingerRotate(Query[] viewQuery, Query[] elementQuery, TapPoint point, int angle)

Perform rotate gesture at the specified location within the element specified by the query. 

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*elementQuery (WebQuery)* - WebQuery object that identifies an element uniquely.

*point (TapPoint)* - Coordinates of rotation center point.

*angle (int)* - The angle in degrees to rotate. The default value is 0.

### Example

```C#
// Rotate the test element starting from 100x, 100y within the element and rotating for 45 degrees
this.ActiveDevice.Web.TwoFingerRotate(Elements.MyScreen.WebView.TestField, new TapPoint(100, 100), 45);
```

```VB
Me.ActiveDevice.Web.TwoFingerRotate(Elements.MyScreen.WebView.TestField, New TapPoint(100, 100), 45)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="wait"></a>
## Wait(int timeout)

Wait specific amount of time before continuing execution.

### Parameters

*timeout (int)* - The amount of time to wait in milliseconds.

### Example

```C#
// Wait for 2 seconds
this.ActiveDevice.Web.Wait(2000);
```

```VB
Me.ActiveDevice.Web.Wait(2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitfor"></a>
## WaitFor(Func&lt;bool&gt; func, int checkInterval, int timeout)

Wait for func to return true or timeouts.

### Parameters

*func (Func&lt;bool&gt;)* - A delegate to a function that is called on every interval.

*checkInterval (int)* - Check interval in milliseconds. Can't be less than or equal to 0.

*timeout (int)* - Timeout interval in milliseconds. Can't be less than or equal to 0. Can't be less than `checkInterval`.

### Example

```C#
// Execute TestMethod1 for 2 sec every 100ms until it returns true or timeouts.
this.ActiveDevice.Web.WaitFor(TestMethod1, 100, 2000);
```

```VB
Me.ActiveDevice.Web.WaitFor(TestMethod1, 100, 2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforscriptresult"></a>
## WaitForScriptResult(Query[] viewQuery, string script, Query[] elementQuery, dynamic result, int checkInterval, int timeout)

Wait until script execution matches specified value or timeout occurs.

### Parameters

*viewQuery (AndroidQuery or IOSQuery)* - native query for target WebView container object.

*script (string)* - String that is transferred and evaled into current web view on every interval.

*elementQuery (WebQuery)* - WebQuery for target element. Element defined by this parameter can be accessed using `targetElement` variable inside the script parameter string.

*result (dynamic)* - Script result to be matched.

*checkInterval (int)* - Check interval in milliseconds. Can't be less than or equal to 0.

*timeout (int)* - Timeout interval in milliseconds. Can't be less than or equal to 0. Can't be less than `checkInterval`.

### Example

```C#
// Wait for a specific result from script - wait for the readyState to return `complete` by checking every 10ms for 2 sec timeout.
this.ActiveDevice.Web.WaitForScriptResult("document.readyState", null, "complete", 10, 2000);
```

```VB
Me.ActiveDevice.Web.WaitForScriptResult("document.readyState", Nothing, "complete", 10, 2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>