---
title: Android
page_title: Android
description: "Telerik Mobile Testing - API Reference - Android"
position: 0
publish: true
slug: ms-android-api
---

# Android

Methods
<select id="methodsSelect" onchange="window.location.hash='#'+event.currentTarget.selectedOptions[0].value;">
 <option value="dragtodisplacement">DragToDisplacement</option>  <option value="dragtopoint">DragToPoint</option>  <option value="elementexists">ElementExists</option>  <option value="elementvisible">ElementVisible</option>  <option value="getpropertyvalue">GetPropertyValue</option>   <option value="pinchin">PinchIn</option>  <option value="pinchout">PinchOut</option>  <option value="pressbackbutton">PressBackButton</option>  <option value="pressmenubutton">PressMenuButton</option>  <option value="pressreturn">PressReturn</option>  <option value="presssearchbutton">PressSearchButton</option>  <option value="screenshot">Screenshot</option>  <option value="selectrow">SelectRow</option>  <option value="setdate">SetDate</option><option value="settext">SetText</option>  <option value="setvalue">SetValue</option>  <option value="swipe">Swipe</option>  <option value="tap">Tap</option>  <option value="tapandhold">TapAndHold</option>  <option value="tapatlocation">TapAtLocation</option>  <option value="tapatpoint">TapAtPoint</option>  <option value="tapcenterleft">TapCenterLeft</option>  <option value="tapcenterright">TapCenterRight</option>  <option value="toggle">Toggle</option>  <option value="twofingerrotate">TwoFingerRotate</option>  <option value="typetext">TypeText</option>  <option value="wait">Wait</option>  <option value="waitfor">WaitFor</option> <option value="waitforelementexists">WaitForElementExists</option>  <option value="waitforelementvisible">WaitForElementVisible</option>  <option value="waitforpropertyvalue">WaitForPropertyValue</option><option value="zoomin">ZoomIn</option> <option value="zoomout">ZoomOut</option> 
</select>

Methods for automating native Android applications.

##Methods

<a id="dragtodisplacement"></a>
## DragToDisplacement (AndroidQuery[] query, TapPoint fromPoint, TapPoint displacement, int steps)

Performs a drag gesture from a point to a displacement from that point within the view specified by the query. Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*fromPoint (TapPoint)* - The X, Y position in the view to start the drag from. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

*displacement (TapPoint)* - The X, Y distance from the fromPoint to end the drag. If null, defaults to center point in view.

*steps (int)* - The amount of touches to generate to complete the drag. Valid values are in the range: 3 - 1000.

### Example

```C#
this.ActiveDevice.Android.DragToDisplacement(elementQry, new TapPoint() { X = 10, Y = 10 }, new TapPoint() { X = -10, Y = -10 }, 20);
```

```VB
Me.ActiveDevice.Android.DragToDisplacement(elementQry, New TapPoint() With {.X = 10, .Y = 10 }, New TapPoint() With {.X = -10, .Y = -10 }, 20)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="dragtopoint"></a>
##  DragToPoint(AndroidQuery[] query, TapPoint fromPoint, TapPoint toPoint, int steps)


Performs a drag gesture from a point to a point within the view specified by the query. Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*fromPoint (TapPoint)* - The X, Y position in the view to start the drag from. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

*toPoint (TapPoint)* - The X, Y position in the view to end the drag. If null, equals the fromPoint. If X, or Y is negative, that value defaults to the X, or Y value of fromPoint. If X or Y is greater than the X or Y of the view, it is still applied as is.

*steps (int)* - The amount of touches to generate to complete the drag. Valid values are in the range: 3 - 1000.

### Example

```C#
this.ActiveDevice.Android.DragToPoint(elementQry, new TapPoint() { X = 10, Y = 10 }, new TapPoint() { X = 10, Y = 10 }, 20);
```
```VB
Me.ActiveDevice.Android.DragToPoint(elementQry, New TapPoint() With {.X = 10, .Y = 10 }, New TapPoint() With { .X = 10, .Y = 10 }, 20)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="elementexists"></a>
## ElementExists (AndroidQuery[] query)

Checks if the view specified by the query exists, and returns the result. Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.ElementExists(elementQry);
```

```VB
Me.ActiveDevice.Android.ElementExists(elementQry)
```

### Return Value

Gets a value indicating whether the element exists.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="elementvisible"></a>
## ElementVisible (AndroidQuery[] query)

Checks if the view specified by the query is visible, and returns the result. Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery*) - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.ElementVisible(elementQry);
```

```VB
Me.ActiveDevice.Android.ElementVisible(elementQry)
```


### Return Value

Gets a value indicating whether the element is visible.

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getpropertyvalue"></a>
## GetPropertyValue (AndroidQuery[] query, string propertyName)

Retrieves the value of a property from a specified view. Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*propertyName (string)* - The string name of the property.

### Example

```C#
this.ActiveDevice.Android.GetPropertyValue(elementQry, "text");
```

```VB
Me.ActiveDevice.Android.GetPropertyValue(elementQry, "text")
```


### Return Value

The String value of the property.

<a href="#methodsSelect">Back to Top</a>
<br><br>


<a id="pinchin"></a>
##PinchIn (AndroidQuery[] query, TapPoint point, int distance, int steps)

Performs a pinch in gesture at the specified location within the view specified by the query. Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The X, Y center point to pinch into in the view. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

*distance (int)* - The distance away from the point to start. Minimum value is 1.

*steps (int)* - The amount of touches to generate to complete the pinch in. Valid values are in the range: 3 - 1000.

### Example

```C#
this.ActiveDevice.Android.PinchIn(elementQry, new TapPoint() { X = 10, Y = 10 }, 100, 50);
```

```VB
Me.ActiveDevice.Android.PinchIn(elementQry, New TapPoint() With {.X = 10, .Y = 10 }, 100, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pinchout"></a>
##PinchOut(AndroidQuery[] query, TapPoint point, int distance, int steps)

Performs a pinch out gesture at the specified location within the view specified by the query. Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The X, Y center point to pinch out from the view. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

*distance (int)* - The distance away from the point to end. Minimum value is 1.

*steps (int)* - The amount of touches to generate to complete the pinch out. Valid values are in the range: 3 - 1000.

### Example

```C#
this.ActiveDevice.Android.PinchOut(elementQry, new TapPoint() { X = 10, Y = 10 }, 100, 50);
```

```VB
Me.ActiveDevice.Android.PinchOut(elementQry, New TapPoint() With { .X = 10, .Y = 10 }, 100, 50)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pressbackbutton"></a>
##PressBackButton ()

Presses the hardware back button.

### Example

```C#
this.ActiveDevice.Android.PressBackButton();
```

```VB
Me.ActiveDevice.Android.PressBackButton()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pressmenubutton"></a>
##PressMenuButton ()

Presses the hardware menu button.

### Example

```C#
this.ActiveDevice.Android.PressMenuButton();
```

```VB
Me.ActiveDevice.Android.PressMenuButton()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="pressreturn"></a>
##PressReturn (AndroidQuery[] query)

Presses the software keyboard return key. <para>If the target is a SearchView, the keypress will target its internal text editing view. Supports subclasses and views of **android.widget.EditText** and **android.widget.SearchView**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.PressReturn(elementQry);
```

```VB
Me.ActiveDevice.Android.PressReturn(elementQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="presssearchbutton"></a>
##PressSearchButton ()

Presses the hardware search button.

### Example

```C#
this.ActiveDevice.Android.PressSearchButton();
```

```VB
Me.ActiveDevice.Android.PressSearchButton()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="screenshot"></a>
## Screenshot ()

Takes a screenshot of the tested UI.

### Example

```C#
this.ActiveDevice.Android.Screenshot();
```

```VB
Me.ActiveDevice.Android.Screenshot()
```
### Return Value

The taken screenshot as array of bytes.

## Screenshot (string fileName)

Takes a screenshot of the tested UI.

### Parameters

*fileName (string)* - The name and location to save the image at.

### Example

```C#
this.ActiveDevice.Android.Screenshot("MyScreenshot.png");
```

```VB
Me.ActiveDevice.Android.Screenshot("MyScreenshot.png")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="selectrow"></a>
##SelectRow (AndroidQuery[] query, int row, int? group = null)

Selects a row in a view specified by the query. If the target is an ExpandableListView, you must also specify a group or the row number will be applied to the group. The group will be expanded before the row is selected within the group. Supports subclasses of: **android.widget.AdapterView**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*row (int)* - Тhe row to select. <para>Positive numbers only.

*group (int)* - Тhe group containing the row to select, for ExpandableListViews. Optional. Positive numbers only.

### Example

```C#
this.ActiveDevice.Android.SelectRow(elementQry, 1);
```

```VB
Me.ActiveDevice.Android.SelectRow(elementQry, 1)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setdate"></a>
##SetDate (AndroidQuery[] query,  DateTime date)

Sets the date on a view specified by the query. Supports views and subclasses of: **android.widget.CalendarView**, **android.widget.DatePicker**, **android.widget.TimePicker**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*date (DateTime)* - The date to set.

### Example

```C#
this.ActiveDevice.Android.SetDate(elementQry,new DateTime(2014,4,12));
```

```VB
Me.ActiveDevice.Android.SetDate(elementQry, New DateTime(2014, 4, 12))
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="settext"></a>
##SetText (AndroidQuery[] query, string text)

Sets the text on a view specified by the query. If the target is a SearchView, this command will target its internal text editing view, and the SearchView will be expanded before text is entered into it.

Supports subclasses and views of **android.widget.EditText** and **android.widget.SearchView**. 

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*text (string)* - Тhe text value to set on the view.

### Example

```C#
this.ActiveDevice.Android.SetText(elementQry, "Test");
```

```VB
Me.ActiveDevice.Android.SetText(elementQry, "Test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="setvalue"></a>
##SetValue (AndroidQuery[] query, double value)

Sets the value of a view specified by the query. 

Supports subclasses of **android.widget.AbsSeekBar** and views and subclasses of **android.widget.NumberPicker**. 

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*value (double)* - The value the view should be set to.

### Example

```C#
this.ActiveDevice.Android.SetValue(elementQry, 60);
```

```VB
Me.ActiveDevice.Android.SetValue(elementQry, 60)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="swipe"></a>
##Swipe (AndroidQuery[] query, SwipeDirection direction)

Performs a swipe gesture across the view specified by the query.

Supports views and subclasses of: **android.view.View**. 

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*direction (SwipeDirection)* - The direction to swipe.

### Example

```C#
this.ActiveDevice.Android.Swipe(elementQry, SwipeDirection.Down);
```

```VB
Me.ActiveDevice.Android.Swipe(elementQry, SwipeDirection.Down)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tap"></a>
##Tap (AndroidQuery[] query, int tapCount = 1, int tapDownDelay = 10, int tapUpDelay = 100)

Performs a tap gesture at the center of the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*tapCount (int)* - How many times to tap. Optional. Default value is 1.

*tapDownDelay (int)* - The amount of time in milliseconds tap down should last. Optional. Default value is 10.

*tapUpDelay (int)* - The amount of time in milliseconds tap up should last, if multiple taps are used. Optional. Default value is 100.

### Example

```C#
this.ActiveDevice.Android.Tap(buttonQry);

this.ActiveDevice.Android.Tap(buttonQry, 2, 1000, 500);
```

```VB
Me.ActiveDevice.Android.Tap(buttonQry)

Me.ActiveDevice.Android.Tap(buttonQry, 2, 1000, 500)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapandhold"></a>
##TapAndHold (AndroidQuery[] query)

Performs a tap-and-hold gesture at the center of the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.TapAndHold(buttonQry);
```

```VB
Me.ActiveDevice.Android.TapAndHold(buttonQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatlocation"></a>
##TapAtLocation (AndroidQuery[] query, int x, int y, int tapCount = 1)

Performs a tap gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*x (int)* - The X coordinate of the location to tap. <para>If negative value is submitted, the value defaults to the center X of the view. If greater than the X of the view, it is still applied as is.

*y (int)* - The Y coordinate of the location to tap. <para>If negative value is submitted, the value defaults to the center Y of the view. If greater than the Y of the view, it is still applied as is.

*tapCount (int)* - How many times to tap. Optional. Default value is 1.

### Example

```C#
this.ActiveDevice.Android.TapAtLocation(buttonQry, 10, 10);

this.ActiveDevice.Android.TapAtLocation(buttonQry, 10, 10, 2);
```

```VB
Me.ActiveDevice.Android.TapAtLocation(buttonQry, 10, 10)

Me.ActiveDevice.Android.TapAtLocation(buttonQry, 10, 10, 2)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapatpoint"></a>
##TapAtPoint (AndroidQuery[] query, TapPoint point = null, int tapCount = 1, int tapDownDelay = 10, int tapUpDelay = 100)

Performs a tap gesture at the specified point within the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The X, Y position to tap in the view. <para>Optional. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

*tapCount (int)* - How many times to tap. <para>Optional. Default value is 1.

*tapDownDelay (int)* - The amount of time in milliseconds tap down should last. Optional. Default value is 10.

*tapUpDelay (int)* - The amount of time in milliseconds tap up should last, if multiple taps are used. Optional. Default value is 100.
### Example

```C#
this.ActiveDevice.Android.TapAtPoint(buttonQry);

this.ActiveDevice.Android.TapAtPoint(buttonQry, new TapPoint() { X=10, Y=10 }, 2, 1000, 500);
```

```VB
Me.ActiveDevice.Android.TapAtPoint(buttonQry)

Me.ActiveDevice.Android.TapAtPoint(buttonQry, New TapPoint() With { .X = 10, .Y = 10 }, 2, 1000, 500)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterleft"></a>
##TapCenterLeft (AndroidQuery[] query)

Performs a tap gesture at the center-left of the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.TapCenterLeft(buttonQry);
```

```VB
Me.ActiveDevice.Android.TapCenterLeft(buttonQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="tapcenterright"></a>
##TapCenterRight (AndroidQuery[] query)

Performs a tap gesture at the center-right of the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.TapCenterRight(buttonQry);
```

```VB
Me.ActiveDevice.Android.TapCenterRight(buttonQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="toggle"></a>
##Toggle (AndroidQuery[] query, bool toggle)

Sets the toggle state of a view specified by the query.

Supports views and subclasses of: **android.widget.CompoundButton**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*toggle (bool)* - Тhe on/off true/false state to apply to the togglable view.

### Example

```C#
this.ActiveDevice.Android.Toggle(elementQry, true);
```

```VB
Me.ActiveDevice.Android.Toggle(elementQry, true)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="twofingerrotate"></a>
##TwoFingerRotate (AndroidQuery[] query, TapPoint point, int angleInDegrees)

Performs a rotate gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **android.view.View**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The X, Y position of origin to rotate around in the view. If null, defaults to center point in view. If X, or Y is negative, that value defaults to the center X, or Y of the view. If X or Y is greater than the X or Y of the view, it is still applied as is.

angleInDegrees (int) - The angle in degrees to rotate.

### Example

```C#
this.ActiveDevice.Android.TwoFingerRotate(elementQry, new TapPoint() {X=20,Y=20 }, 180);
```

```VB
Me.ActiveDevice.Android.TwoFingerRotate(elementQry, New TapPoint() With { .X = 20, .Y = 20 }, 180)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="typetext"></a>
##TypeText (AndroidQuery[] query, string text)

Types the text into a view specified by the query. If the target is a SearchView, the typing will target its internal text editing view, and the SearchView will be expanded before text is entered into it.

Supports subclasses and views of **android.widget.EditText** and **android.widget.SearchView**.

### Parameters
*query (AndroidQuery)* - Identifies an element uniquely.

*text (string)* -The text value to type into the view.

### Example

```C#
this.ActiveDevice.Android.TypeText(elementQry, "Test");
```

```VB
Me.ActiveDevice.Android.TypeText(elementQry, "Test")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="wait"></a>
##Wait (int miliseconds)

Waits an arbitrary amount of time before continuing execution.

### Parameters
*miliseconds (int)* - The amount of time to wait in milliseconds.<para>Positive numbers only.

### Example

```C#
this.ActiveDevice.Android.Wait(1000);
```

```VB
Me.ActiveDevice.Android.Wait(1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitfor"></a>
##WaitFor (Func \<bool> func, int checkInterval, int timeout)

Executes periodic verifications against a custom condition and times out if the condition is not met.

### Parameters
*func (\<bool> func)* - The custom condition to verify.

*checkInterval (int)* - The interval between verification calls. Positive numbers only.

*timeout (int)* - The overall number of milliseconds to wait. Positive numbers only. Cannot be less than 'checkInterval'.

### Example

```C#
this.ActiveDevice.Android.WaitFor(new Func<bool>(() => { Random r = new Random(); return (r.Next(2) % 2 == 0); }), 100, 200); 
```

```VB
Me.ActiveDevice.Android.WaitFor(New Func(Of Boolean)(Function() 
Dim r As New Random()
Return (r.[Next](2) Mod 2 = 0)

End Function), 100, 200)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforelementexists"></a>
##WaitForElementExists (AndroidQuery[] query, bool exists, int checkInterval, int timeout)

Executes periodic verifications against an element query to ensure element existence or times out.

Supports views and subclasses of: android.view.View.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*exists (bool)* - The expected command value.

*checkInterval (int)* - The interval between verification calls. Positive numbers only.

*timeout (int)* - The overall number of milliseconds to wait. Positive numbers only. Cannot be less than 'checkInterval'.

### Example

```C#
this.ActiveDevice.Android.WaitForElementExists(elementQry, true, 100, 1000);
```

```VB
Me.ActiveDevice.Android.WaitForElementExists(elementQry, true, 100, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforelementvisible"></a>
##WaitForElementVisible (AndroidQuery[] query, bool visible, int checkInterval, int timeout)

Executes periodic verifications against an element query to ensure element visibility or times out.

Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*visible (bool)* - The expected command value.

*checkInterval (int)* - The interval between verification calls. Positive numbers only.

*timeout (int)* - The overall number of milliseconds to wait. Positive numbers only. Cannot be less than 'checkInterval'.

### Example

```C#
this.ActiveDevice.Android.WaitForElementVisible(elementQry, true, 100, 1000);
```

```VB
Me.ActiveDevice.Android.WaitForElementVisible(elementQry, true, 100, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="waitforpropertyvalue"></a>
##WaitForPropertyValue (AndroidQuery[] query, string propertyName, string propertyValue, int checkInterval, int timeout)  

Executes periodic verifications against an element property to ensure its value or times out.

Supports views and subclasses of: **android.view.View**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

*propertyName (string)* - The string name of the property.

*propertyValue (string)* - The expected property value.

*checkInterval (int)* - The interval between verification calls. Positive numbers only.

*timeout (int)* - The overall number of milliseconds to wait. Positive numbers only. Cannot be less than 'checkInterval'.

### Example

```C#
this.ActiveDevice.Android.WaitForPropertyValue(elementQry, "text", "t", 100, 1000);
```

```VB
Me.ActiveDevice.Android.WaitForPropertyValue(elementQry, "text", "t", 100, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>
<a id="zoomin"></a>
##ZoomIn(AndroidQuery[] query)

Taps on the zoom in button of a ZoomControls.

Supports views and subclasses of **android.widget.ZoomControls**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.ZoomIn(elementQry);
```

```VB
Me.ActiveDevice.Android.ZoomIn(elementQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>
<a id="zoomout"></a>
##ZoomOut(AndroidQuery[] query)

Taps on the zoom out button of a ZoomControls.

Supports views and subclasses of **android.widget.ZoomControls**.

### Parameters

*query (AndroidQuery)* - Identifies an element uniquely.

### Example

```C#
this.ActiveDevice.Android.ZoomOut(elementQry);
```

```VB
Me.ActiveDevice.Android.ZoomOut(elementQry)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>