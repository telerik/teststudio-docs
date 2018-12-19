---
title: Web
page_title: Web
description: "Telerik Mobile Testing - API Reference - Web"
position: 0
publish: true
slug: ms-web-api
---

# Web

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
<option value="navigatetourl">NavigateToUrl</option>
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
<option value="waitforurl">WaitForUrl</option>
</select>

Methods for automating web applications.

##Methods

<a id="click"></a>
## Click(Query[] query)

Perform a click on an element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// This will perform a web click action on the provided element
this.ActiveDevice.Web.Click(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.DoubleClick(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="doubleclick"></a>
## DoubleClick(Query[] query)

Perform a double click on an element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// This will perform a web double click on the provided element
this.ActiveDevice.Web.DoubleClick(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.DoubleClick(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="drag"></a>
## Drag(Query[] query, int offsetX, int offsetY)

Drag an element to specific point.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*offsetX (int)* - Destination point horizontal offset from element center.

*offsetY (int)* - Destination point vertical offset from element center.

### Example

```C#
// This will drag a draggable web element to 100x,300y point realtive to the center of the provided element
this.ActiveDevice.Web.Drag(Elements.MyScreen.DragElement, 100,300);
```

```VB
Me.ActiveDevice.Web.Drag(Elements.MyScreen.DragElement, 100, 300)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtodisplacement"></a>
## DragToDisplacement(Query[] query, TapPoint fromPoint, TapPoint displacement, int steps)

Performs drag gesture from a point to a displacement within the element specified by the query.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*fromPoint (TapPiont)* - Starting point of drag gesture. If null, defaults to center point in view.

*displacement (TapPiont)* - Displacement, represented as point object. If null, defaults to center point of element.

*steps (int)* - The amount of touches to generate to complete the drag gesture.  Valid values are in the range: 3 - 1000.

### Example

```C#
// This will drag an item in web view from 0x,0y point (relative to the element) to 100x,300y point relative to the first TapPoint(0,0) in 150 simulated touches
this.ActiveDevice.Web.DragToDisplacement(Elements.MyScreen.DragElement, new TapPoint(0,0), new TapPoint(100,300), 150);
```

```VB
Me.ActiveDevice.Web.DragToDisplacement(Elements.MyScreen.DragElement, New TapPoint(0, 0), New TapPoint(100, 300), 150)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtoelement"></a>
## DragToElement(Query[] dragElementQuery, Query[] toElementQuery)

Drag an element over another element.

### Parameters

*dragElementQuery (WebQuery)* - Query object that identifies element to be dragged. The element to be dragged must be draggable.

*toElementQuery (WebQuery)* - Query object that identifies element the dragged element will be dragged over.

### Example

```C#
// Drag element dragElement on top of element TestField
this.ActiveDevice.Web.DragToElement(Elements.MyScreen.DragElement, Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.DragToElement(Elements.MyScreen.DragElement, Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtopoint"></a>
## DragToPoint(Query[] query, TapPoint fromPoint, TapPoint toPoint, int steps )

Drag an element over another element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*fromPoint (TapPiont)* - Starting point of drag gesture. If null, defaults to center point of element.

*displacement (TapPiont)* - Finishing point of drag gesture. If null, defaults to center point of element.

*steps (int)* - The amount of touches to generate to complete the drag gesture.  Valid values are in the range: 3 - 1000.

### Example

```C#
// This will drag an item in web view from 0x,0y point inside the specified element to 100x,300y point relative to the element in 150 simulated touches
this.ActiveDevice.Web.DragToPoint(Elements.MyScreen.DragElement, new TapPoint(0,0), new TapPoint(100,300), 150);
```

```VB
Me.ActiveDevice.Web.DragToPoint(Elements.MyScreen.DragElement, New TapPoint(0, 0), New TapPoint(100, 300), 150)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="executescript"></a>
## ExecuteScript(string script, Query[] query)

Execute a script into web browser.

### Parameters

*script (string)* - String that is transferred to application under test and evaled into current web page.

*query (WebQuery)* - Query for target element. Element defined by this parameter can be accessed using targetElement variable inside the script parameter string.

### Example

```C#
// Executes the script inside the string parameter on the web app under test. Deprecated: Use getScriptResult instead.
this.ActiveDevice.Web.ExecuteScript("document.getElementsByTagName(\"div\")");
```

```VB
Me.ActiveDevice.Web.ExecuteScript("document.getElementsByTagName(""div"")")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getattribute"></a>
## GetAttribute(Query[] query, string attrName)

Get attribute value of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*attrName (string)* - Name of the attribute.

### Example

```C#
// Get attribute will return the id attribute of DragElement as string
string idAttribute = this.ActiveDevice.Web.GetAttribute(Elements.MyScreen.DragElement, "id");
```

```VB
Dim idAttribute As String = Me.ActiveDevice.Web.GetAttribute(Elements.MyScreen.DragElement, "id")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getchecked"></a>
## GetChecked(Query[] query)

Gets checked state of specific checkbox element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.


### Example

```C#
// Returns the checked state of the checkBox as boolean
bool state = this.ActiveDevice.Web.GetChecked(Elements.MyScreen.CheckBox);
```

```VB
Dim state As Boolean = Me.ActiveDevice.Web.GetChecked(Elements.MyScreen.CheckBox)
```

### Return Value

The checked state of specific checkbox element.

<a href="#methodsSelect">Back to Top</a>
<br><br>


<a id="getcolumncount"></a>
## GetColumnCount(Query[] query, uint rowIndex)

Gets checked state of specific checkbox element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*rowIndex (unit)* - Index of row which column count is needed.

### Example

```C#
// Returns the number of columns in the desired table row
uint count = this.ActiveDevice.Web.GetColumnCount(Elements.MyScreen.TableView, 1);
```

```VB
Dim count As UInteger = Me.ActiveDevice.Web.GetColumnCount(Elements.MyScreen.TableView, 1)
```

### Return Value

The number of columns in a particular row in table element.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="gethtml"></a>
## GetHtml(Query[] query)

Get inner html of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Gets the inner HTML of CheckBox
string html = this.ActiveDevice.Web.GetHtml(Elements.MyScreen.CheckBox);
```

```VB
Dim html As String = Me.ActiveDevice.Web.GetHtml(Elements.MyScreen.CheckBox)
```

### Return Value

The inner html of specific element as string.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getinerror"></a>
## GetInError(Query[] query)

Gets error state of audio/video element. This function returns inconsistent results for mobile browsers. Use only with desktop browsers.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
bool statePlayer = this.ActiveDevice.Web.GetInError(Elements.MyScreen.Player);
```

```VB
Dim statePlayer As Boolean = Me.ActiveDevice.Web.GetInError(Elements.MyScreen.Player)
```

### Return Value

True if control is in error state, otherwise false.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getpaused"></a>
## GetPaused(Query[] query)

Get paused state of audio/video element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
bool statePaused = this.ActiveDevice.Web.GetPaused(Elements.MyScreen.Player);
```

```VB
Dim statePaused As Boolean = Me.ActiveDevice.Web.GetPaused(Elements.MyScreen.Player)
```

### Return Value

True if audio/video element is paused, otherwise false.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getrowcount"></a>
## GetRowCount(Query[] query)

Get number of rows of a table element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Returns the number of rows in the TableView
uint rowCount = this.ActiveDevice.Web.GetRowCount(Elements.MyScreen.TableView);
```

```VB
Dim rowCount As UInteger = Me.ActiveDevice.Web.GetRowCount(Elements.MyScreen.TableView)
```

### Return Value

The number of rows of a table element.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getscriptresult"></a>
## GetScriptResult(string script, Query[] query)

Get number of rows of a table element.

**Note:** In order you se this method you should add reference assembly to **Microsoft.CSharp.dll** and **System.Core.dll** from the <a href="/test-studio-mobile/getting-started-mb/project-settings" target="_blank">project settings</a>.

### Parameters

*script (string)* - String that is transferred to application under test and evaled into current web page.

*query (WebQuery)* - Query for target element. Element defined by this parameter can be accessed using targetElement variable inside the script parameter string.

### Example

```C#
// This will execute the script in the string and save the result as object
object result = this.ActiveDevice.Web.GetScriptResult("document.getElementsByTagName(\"div\")");
```

```VB
Dim result As Object = Me.ActiveDevice.Web.GetScriptResult("document.getElementsByTagName(""div"")")
```

### Return Value

Result of script execution.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedindex"></a>
## GetSelectedIndex(Query[] query)

Get selected index of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Get the selected index of the Select element (select type element), more than one items can be selected
uint[] index = this.ActiveDevice.Web.GetSelectedIndex(Elements.MyScreen.Select);
```

```VB
Dim index As UInteger() = Me.ActiveDevice.Web.GetSelectedIndex(Elements.MyScreen.Select)
```

### Return Value

Array of selected indexes.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedtext"></a>
## GetSelectedText(Query[] query)

Get selected text values of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Gets the selected text/s from selected items in the select element
string[] selectedText = this.ActiveDevice.Web.GetSelectedText(Elements.MyScreen.Select);
```

```VB
Dim selectedText() As String = Me.ActiveDevice.Web.GetSelectedText(Elements.MyScreen.Select)
```

### Return Value

Array of selected text values.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getselectedvalue"></a>
## GetSelectedValue(Query[] query)

Get selected value strings of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Gets the selected value/s from selected items in the select element
string[] selectedValue = this.ActiveDevice.Web.GetSelectedValue(Elements.MyScreen.Select);
```

```VB
Dim selectedValue As String() = Me.ActiveDevice.Web.GetSelectedValue(Elements.MyScreen.Select)
```

### Return Value

Array of selected value strings.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getstyle"></a>
## GetStyle(Query[] query, string styleProp)

Get specific style property value.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*styleProp (string)* - Name of the style attribute.

### Example

```C#
// Get style will return the width style in the example
string style = this.ActiveDevice.Web.GetStyle(Elements.MyScreen.TestField, "width");
```

```VB
Dim style As String = Me.ActiveDevice.Web.GetStyle(Elements.MyScreen.TestField, "width")
```

### Return Value

The value of requested style attribute.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="gettextcontent"></a>
## GetTextContent(Query[] query)

Get text content of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// This will return the text content of the test element
string textContent = this.ActiveDevice.Web.GetTextContent(Elements.MyScreen.TestField);
```

```VB
Dim textContent As String = Me.ActiveDevice.Web.GetTextContent(Elements.MyScreen.TestField)
```

### Return Value

Text content of specified element.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getvalue"></a>
## GetValue(Query[] query)

Get value of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// This will return the value of the test element
string valueOfElement = this.ActiveDevice.Web.GetValue(Elements.MyScreen.TestField);
```

```VB
Dim valueOfElement As String = Me.ActiveDevice.Web.GetValue(Elements.MyScreen.TestField)
```

### Return Value

Value of specified element.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="hoverover"></a>
## HoverOver(Query[] query)

Perform a mouse hover over an element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Perform a mouse hover action
this.ActiveDevice.Web.HoverOver(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.HoverOver(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>


<a id="navigatetourl"></a>
## NavigateToUrl(string url)

Make the browser under test navigate to specific URL.

### Parameters

*url (string)* - The URL to navigate to.

### Example

```C#
// Make the browser under test navigate to http://telerik.com
this.ActiveDevice.Web.NavigateToUrl("http://telerik.com");
```

```VB
Me.ActiveDevice.Web.NavigateToUrl("http://telerik.com")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pinchin"></a>
## PinchIn(Query[] query, TapPoint point, int distance, int steps)

Perform pinch in gesture at the specified location within the view specified by the query. 

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*point (TapPoint)* - Coordintes of pinch center point. If null, defaults to center point of element.

*distance (int)* - Distance away from the center to start. Minimum value is 20.

*steps (int)* - The amount of touches to generate to complete the pinch. Valid values are in the range: 3 - 1000.

### Example

```C#
// Perform a pinch in over the test element where the pinch will start at 100x,100y point within the element and will pinchIn 20px in 50 simulated touches
this.ActiveDevice.Web.PinchIn(Elements.MyScreen.TestField, new TapPoint(100,100), 20, 50);
```

```VB
Me.ActiveDevice.Web.PinchIn(Elements.MyScreen.TestField, New TapPoint(100, 100), 20, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pinchout"></a>
## PinchOut(Query query, TapPoint point, int distance, int steps)

Perform pinch out gesture at the specified location within the view specified by the query.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*point (TapPoint)* - Coordintes of pinch center point. If null, defaults to center point of element.

*distance (int)* - Distance away from the center to start. Minimum value is 20.

*steps (int)* - The amount of touches to generate to complete the pinch. Valid values are in the range: 3 - 1000.

### Example

```C#
// Perform a pinch in over the test element where the pinch out will start at 100x,100y point within the element and will pinchOut 20px in 50 simulated touches
this.ActiveDevice.Web.PinchOut(Elements.MyScreen.TestField, new TapPoint(100,100), 20, 50);
```

```VB
Me.ActiveDevice.Web.PinchOut(Elements.MyScreen.TestField, New TapPoint(100, 100), 20, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="presskey"></a>
## PressKey(Query[] query, int keyCode, bool alt, bool ctrl, bool shift)

Invoke press key event on specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*keyCode (int)* - Code of the key.

*alt (boolean)* - Boolean value indicating whether ALT is pressed. The default is false.

*ctrl (boolean)* - Boolean value indicating whether CTRL is pressed. The default is false.

*shift (boolean)* - Boolean value indicating whether SHIFT is pressed. The default is false.

### Example

```C#
// This will invoke the press CAPS LOCK key event (with code 20) over the test element 
this.ActiveDevice.Web.PressKey(Elements.MyScreen.TestField, 20);
```

```VB
Me.ActiveDevice.Web.PressKey(Elements.MyScreen.TestField, 20)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="rightclick"></a>
## RightClick(Query[] query)

Perform a right click on an element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Perform a right click on the test element
this.ActiveDevice.Web.RightClick(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.RightClick(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="scroll"></a>
## Scroll(Query[] query, int x = 0, int y = 0)

Scroll the web page to any element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*x (int)* - The X confidantes of the specific element.

*y (int)* - The Y confidantes of the specific element.



### Example

```C#
// Scroll to a 300x, 300y point relative to the element
this.ActiveDevice.Web.Scroll(Elements.MyScreen.TestField, 300, 300);
```

```VB
Me.ActiveDevice.Web.Scroll(Elements.MyScreen.TestField, 300, 300)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="scrolltoelement"></a>
## ScrollToElement(Query[] query)

Scroll the web page to any element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Scroll to the test element to make it visible on the screen
this.ActiveDevice.Web.ScrollToElement(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.ScrollToElement(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setattribute"></a>
## SetAttribute(Query[] query, string attrName, string attrValue)

Set attribute of specific element to a specific value.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*attrName (string)* - Name of the attribute.

*attrValue (string)* - Value to be set.

### Example

```C#
// Set the id attribute of the test element to test
this.ActiveDevice.Web.SetAttribute(Elements.MyScreen.TestField, "id", "test");
```

```VB
Me.ActiveDevice.Web.SetAttribute(Elements.MyScreen.TestField, "id", "test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setchecked"></a>
## SetChecked(Query[] query, bool checkedValue)

Sets checked state of specific checkbox element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*attrName (boolean)* - Checked state value to be set.

### Example

```C#
// Set the state of the checklbox to false
this.ActiveDevice.Web.SetChecked(Elements.MyScreen.CheckBox, false);
```

```VB
Me.ActiveDevice.Web.SetChecked(Elements.MyScreen.CheckBox, False)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="sethtml"></a>
## SetHtml(Query[] query, string html)

Set inner html of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*html (sting)* - The Html that will be inserted in the specific element.

### Example

```C#
// this will set the '<label>text<label>' html to the test element
this.ActiveDevice.Web.SetHtml(Elements.MyScreen.TestField, "<label>text<label>");
```

```VB
Me.ActiveDevice.Web.SetHtml(Elements.MyScreen.TestField, "<label>text<label>")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setpaused"></a>
## SetPaused(Query[] query, bool pausedState)

Set paused state of audio/video element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*pausedState (boolean)* - Paused state to be set.

### Example

```C#
// This method will pause the video player
this.ActiveDevice.Web.SetPaused(Elements.MyScreen.Player, true);
```

```VB
Me.ActiveDevice.Web.SetPaused(Elements.MyScreen.Player, True)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedindex"></a>
## SetSelectedIndex(Query[] query, params uint[] indexes)

Set selected index of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*indexes (uint array)* - Array of selected indexes.

### Example

```C#
// Selects element with index 3 from the select element
this.ActiveDevice.Web.SetSelectedIndex(Elements.MyScreen.Select, 3);
```

```VB
Me.ActiveDevice.Web.SetSelectedIndex(Elements.MyScreen.Select, 3)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedtext"></a>
## SetSelectedText(Query[] query, params string[] text)

Set selected text values of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*text (string array)* - Array of selected text values.

### Example

```C#
// Selects a specific item by its text in select element
this.ActiveDevice.Web.SetSelectedText(Elements.MyScreen.Select, "text");
```

```VB
Me.ActiveDevice.Web.SetSelectedText(Elements.MyScreen.Select, "text")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setselectedvalue"></a>
## SetSelectedValue(Query[] query, params string[] values)

Set selected value strings of select element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*values (string array)* - Array of values.

### Example

```C#
// Set selected value of select element
this.ActiveDevice.Web.SetSelectedValue(Elements.MyScreen.Select, "value");
```

```VB
Me.ActiveDevice.Web.SetSelectedValue(Elements.MyScreen.Select, "value")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setstyle"></a>
## SetStyle(Query[] query, string styleProp, string styleValue)

Set specific style property value.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*styleProp (string)* - Name of the style attribute.

*styleValue (string)* - Value to be set.

### Example

```C#
// This will set the width of the testElement to 5-px
this.ActiveDevice.Web.SetStyle(Elements.MyScreen.TestField, "width", "50px");
```

```VB
Me.ActiveDevice.Web.SetStyle(Elements.MyScreen.TestField, "width", "50px")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="settextcontent"></a>
## SetTextContent(Query[] query, string textContent)

Set text content of specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*textContent (string)* - Text content to be set.

### Example

```C#
// This will set the text content of the test element
this.ActiveDevice.Web.SetTextContent(Elements.MyScreen.TestField, "textToSet");
```

```VB
Me.ActiveDevice.Web.SetTextContent(Elements.MyScreen.TestField, "textToSet")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setvalue"></a>
## SetValue(Query[] query, string value)

Set value to specific element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*value (string)* - Value to be set.

### Example

```C#
// Set "test" value to the test element
this.ActiveDevice.Web.SetValue(Elements.MyScreen.TestField, "test");
```

```VB
Me.ActiveDevice.Web.SetValue(Elements.MyScreen.TestField, "test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="swipe"></a>
## Swipe(Query[] query, SwipeDirection direction)
## Swipe(Query[] query, SwipeDirection direction, int swipeDistance = 200)

Perform a swipe gesture across the view specified by the query. 

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*direction (SwipeDirection)* - Direction to swipe.

*swipeDistance (int)* - Swipe distance, default is '200'.

### Example

```C#
// Swipe right on the test element
this.ActiveDevice.Web.Swipe(Elements.MyScreen.TestField, SwipeDirection.Right);
```

```VB
Me.ActiveDevice.Web.Swipe(Elements.MyScreen.TestField, SwipeDirection.Right)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tap"></a>
## Tap(Query[] query, int tapCount, int tapDownDelay, int tapUpDelay)

Tap an element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

*tapDownDelay (int)* - Tap down delay in miliseconds. Min value 50.

*tapUpDelay (int)* - Tap up delay in miliseconds. Min value 50.

### Example

```C#
// Tap action on the test element
this.ActiveDevice.Web.Tap(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.Tap(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapandhold"></a>
## TapAndHold(Query[] query)

Perform tap-and-hold gesture at the center of the element.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Tap and hold action on the test element
this.ActiveDevice.Web.TapAndHold(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.TapAndHold(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatlocation"></a>
## TapAtLocation(Query[] query, int X, int Y, int tapCount)

Tap an element on particular location. 

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*X (int)* - X coordinate of point to be tapped.

*Y (int)* - Y coordinate of point to be tapped.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

### Example

```C#
// Tap at 50x,50y point within the test element
this.ActiveDevice.Web.TapAtLocation(Elements.MyScreen.TestField, 50, 50, 1);
```

```VB
Me.ActiveDevice.Web.TapAtLocation(Elements.MyScreen.TestField, 50, 50, 1)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatpoint"></a>
## TapAtPoint(Query[] query, TapPoint point, int tapCount, int tapDownDelay, int tapUpDelay)

Tap an element on particular point. 

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*point (TapPoint)* - Point inside element to be tapped.

*tapCount (int)* - Numbers of taps to be performed. Min value 1.

*tapDownDelay (int)* - Tap down delay in miliseconds. Min value 50.

*tapUpDelay (int)* - Tap up delay in miliseconds. Min value 50.

### Example

```C#
// Tap at 50x,50y point within the test element
this.ActiveDevice.Web.TapAtPoint(Elements.MyScreen.TestField, new TapPoint(50,50));
```

```VB
Me.ActiveDevice.Web.TapAtPoint(Elements.MyScreen.TestField, New TapPoint(50, 50))
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterleft"></a>
## TapCenterLeft(Query[] query)

Tap an element on center left point.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Tap an element on center left point.
this.ActiveDevice.Web.TapCenterLeft(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.TapCenterLeft(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterright"></a>
## TapCenterRight(Query[] query)

Tap an element on center right point.

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

### Example

```C#
// Tap an element on center right point.
this.ActiveDevice.Web.TapCenterRight(Elements.MyScreen.TestField);
```

```VB
Me.ActiveDevice.Web.TapCenterRight(Elements.MyScreen.TestField)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="twofingerrotate"></a>
## TwoFingerRotate(Query[] query, TapPoint point, int angle)

Perform rotate gesture at the specified location within the view specified by the query. 

### Parameters

*query (WebQuery)* - Query object that identifies an element uniquely.

*point (TapPoint)* - Coordinates of rotation center point.

*angle (int)* - The angle in degrees to rotate. The default value is 0.

### Example

```C#
// Rotate the test element starting from 100x,100y within the element and rotating for 45 degrees
this.ActiveDevice.Web.TwoFingerRotate(Elements.MyScreen.TestField, new TapPoint(100,100), 45);
```

```VB
Me.ActiveDevice.Web.TwoFingerRotate(Elements.MyScreen.TestField, New TapPoint(100, 100), 45)
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
## WaitFor(Func<bool> func, int checkInterval, int timeout)

Wait for func to return true or timeout.

### Parameters

*func (Func<bool>)* - Function that is called on every interval.

*checkInterval (int)* - Check interval in milliseconds.

*timeout (int)* - Timeout interval in milliseconds.

### Example

```C#
// Execute TestMethod1 for 2 sec every 100ms until it returns true of false
this.ActiveDevice.Web.WaitFor(TestMethod1, 100, 2000);
```

```VB
Me.ActiveDevice.Web.WaitFor(TestMethod1, 100, 2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforscriptresult"></a>
## WaitForScriptResult(string script, Query[] query, dynamic result, int checkInterval, int timeout)

Wait for func to return true or timeout.

### Parameters

*script (string)* - Function that is called on every interval.

*query (WebQuery)* - Query for target element. Element defined by this parameter can be accessed using targetElement variable inside the script parameter string.

*result (dynamic)* - Script result to be matched.

*checkInterval (int)* - Delay in milliseconds between checks.

*timeout (int)* - Number of milliseconds to wait for script result to match.

### Example

```C#
// Wait for a specific result from script - waith for the readyState to return complete by checking every 10ms for 2 sec timeout
this.ActiveDevice.Web.WaitForScriptResult("document.readyState", null, "complete", 10, 2000);
```

```VB
Me.ActiveDevice.Web.WaitForScriptResult("document.readyState", Nothing, "complete", 10, 2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforurl"></a>
## WaitForUrl(string url, int checkInterval, int timeout)

Wait until current url matches specified value or timeout occurs.

### Parameters

*url (string)* - Url to match.

*checkInterval (int)* - Delay in milliseconds between checks.

*timeout (int)* - Number of milliseconds to wait for script result to match.

### Example

```C#
// This will wait for the telerik.com page to load and will check every 10ms for 2 seconds
this.ActiveDevice.Web.WaitForUrl("http://telerik.com", 10, 2000);
```

```VB
Me.ActiveDevice.Web.WaitForUrl("http://telerik.com", 10, 2000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

