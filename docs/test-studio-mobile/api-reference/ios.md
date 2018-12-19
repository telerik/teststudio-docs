---
title: iOS
page_title: iOS
description: "Telerik Mobile Testing - API Reference - iOS"
position: 0
publish: true
slug: ms-ios-api
---

# iOS

Methods
<select id="methodsSelect" onchange="window.location.hash='#'+event.currentTarget.selectedOptions[0].value;">
 <option value="DragCellToIndexPath">DragCellToIndexPath</option>  <option value="DragToDisplacement">DragToDisplacement</option> <option value="DragToPoint">DragToPoint</option>  <option value="ElementExists">ElementExists</option>  <option value="elementvisible">ElementVisible</option>  <option value="getpropertyvalue">GetPropertyValue</option>   <option value="PressDismiss">PressDismiss</option>  <option value="PressReturn">
PressReturn</option>  <option value="PinchIn">PinchIn</option>  <option value="PinchOut">PinchOut</option><option value="ScrollToItem">ScrollToItem</option>  <option value="ScrollToRow">ScrollToRow</option> <option value="SelectRowInComponent">SelectRowInComponent</option>  <option value="SelectRow">SelectRow</option>  <option value="SelectItem">SelectItem</option>  <option value="SetDate">SetDate</option>    <option value="SetText">SetText</option>  <option value="SetValue">SetValue</option>  <option value="Screenshot">Screenshot</option>  <option value="Swipe">Swipe</option>  <option value="Tap">Tap</option><option value="TapAtLocation">TapAtLocation</option>  <option value="TapAtPoint">TapAtPoint</option>  <option value="TapCenterLeft">TapCenterLeft</option>  <option value="TapCenterRight">TapCenterRight</option>  <option value="TapAndHold">TapAndHold</option>  <option value="TypeText">TypeText</option>  <option value="TapSubviewAtIndex">TapSubviewAtIndex</option> 
<option value="Toggle">Toggle</option> <option value="TwoFingerRotate">TwoFingerRotate</option> <option value="Wait">Wait</option>
<option value="WaitForElementExists">WaitForElementExists</option>  <option value="WaitForElementVisible">WaitForElementVisible</option> <option value="WaitForPropertyValue">WaitForPropertyValue</option> 

</select>

Methods for automating native iOS applications.

##Methods


<a id="DragCellToIndexPath"></a>
## DragCellToIndexPath(IOSQuery[] query, int fromRow, int fromSection, int toRow, int toSection)

Drags the cell from the specified row and section to a different row and section.

Supports views and subclasses of: **UITableView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*fromRow (int)* - The row to drag from.

*fromSection (int)* - The section that contains the fromRow.

*toRow (int)* - The row to drag to.

*toSection (int)* - The section that contains the toRow.

### Example

```C#
// This will drag table cell from row 1 to row 4 in the TableView
this.ActiveDevice.IOS.DragCellToIndexPath(Elements.MyScreen.UITableView, 1,0,4,0);	
```

```VB
Me.ActiveDevice.IOS.DragCellToIndexPath(Elements.MyScreen.UITableView, 1,0,4,0)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="DragToDisplacement"></a>
## DragToDisplacement(IOSQuery[] query, TapPoint fromPoint, TapPoint displacement, int steps)

Performs a drag gesture from a location to a displacement from that location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*fromPoint (TapPoint)* - The x, y position in the view to start the drag from.

*displacement (TapPoint)* - The x, y distance from the fromPoint to end the drag.

*steps (int)* - The amount of touches to generate to complete the drag. 3 minimum and not more than 1000.

### Example

```C#
// This will drag an item in UIView from 100x,100y point to 100x,300y point relative to that UIView using 200 touches
this.ActiveDevice.IOS.DragToDisplacement(Elements.MyScreen9.UIView, new TapPoint(100,100),new TapPoint(100,300),200);
```

```VB
Me.ActiveDevice.IOS.DragToDisplacement(Elements.MyScreen9.UIView, New TapPoint(100, 100), New TapPoint(100, 300), 200)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="DragToPoint"></a>
## DragToPoint(IOSQuery[] query, TapPoint fromPoint, TapPoint toPoint, int steps)

Performs a drag gesture from a location to a location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*fromPoint (TapPoint)* - The x, y position in the view to start the drag from.

*toPoint (TapPoint)* - The x, y position in the view to end the drag.

*steps (int)* - The amount of touches to generate to complete the drag. 3 minimum and not more than 1000.

### Example

```C#
// This will drag an item in UIView from 100x,100y point to 100x,300y point in the same UIView using 200 touches
this.ActiveDevice.IOS.DragToPoint(Elements.MyScreen9.UIView, new TapPoint(100,100),new TapPoint(100,300),200);
```

```VB
Me.ActiveDevice.IOS.DragToPoint(Elements.MyScreen9.UIView, New TapPoint(100, 100), New TapPoint(100, 300), 200)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="ElementExists"></a>
## ElementExists(IOSQuery[] query)

Checks if the view specified by the query exists, and returns the result as boolean.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

### Return Value

Exists boolean

### Example

```C#
// This will verify that the UISwitch exists and return the result as booelan 
bool exists = this.ActiveDevice.IOS.ElementExists(Elements.MyScreen9.UISwitch);
```

```VB
Me.ActiveDevice.IOS.ElementExists(Elements.MyScreen9.UISwitch)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="elementvisible"></a>
## ElementVisible(IOSQuery[] query)

Checks if the view specified by the query is visible, and returns the result as boolean.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

### Return Value

isVisible boolean

### Example

```C#
// This will verify that the UISwitch is visible on the screen and return the result as booelan 
bool visible = this.ActiveDevice.IOS.ElementVisible(Elements.MyScreen9.UISwitch);
```

```VB
Dim visible As Boolean = Me.ActiveDevice.IOS.ElementVisible(Elements.MyScreen9.UISwitch)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="getpropertyvalue"></a>
## GetPropertyValue(IOSQuery[] query, string propertyName)

Retrieves the value of a property from a specified view.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*propertyName (string)* - The string name of the property.

### Return Value

The String value of the property.

### Example

```C#
// This will get the value of "text" property of a label and save it in the LabelText string
string LabelText = this.ActiveDevice.IOS.GetPropertyValue(Elements.MyScreen1.UILabel, "text");
```

```VB
Dim LabelText As String = Me.ActiveDevice.IOS.GetPropertyValue(Elements.MyScreen1.UILabel, "text")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="PressDismiss"></a>
## PressDismiss()

Presses dismiss on the keyboard.

### Example

```C#
// This will press the dismiss key on the keyboard
this.ActiveDevice.IOS.PressDismiss();
```

```VB
Me.ActiveDevice.IOS.PressDismiss()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="PressReturn"></a>
## PressReturn()

Presses return on the keyboard.

### Example

```C#
// This will press the return key on the keyboard
this.ActiveDevice.IOS.PressReturn();
```

```VB
Me.ActiveDevice.IOS.PressReturn()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="PinchIn"></a>
## PinchIn(IOSQuery[] query, TapPoint point, int distance, int steps)

Performs a pinch in gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The x, y center point to pinch into the view. If null, defaults to center point in view.

*distance (int)* - The distance away from the center point to start the pinch. Cannot be less than 1.

*steps (int)* - The amount of touches to generate to complete the pinch in. Cannot be less than 3 and more than 1000.

### Example

```C#
// This will Pinch In over the center of the UIView and with each finger at 20 pixels from the center of the UIView. The Pinch in action will performed in 100 "touches".
this.ActiveDevice.IOS.PinchIn(Elements.MyScreen9.UIView,null,20,100);
```

```VB
Me.ActiveDevice.IOS.PinchIn(Elements.MyScreen9.UIView,null,20,100)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="PinchOut"></a>
## PinchOut(IOSQuery[] query, TapPoint point, int distance, int steps)

Performs a pinch out gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The x, y position to pinch out from in the view. If null, defaults to center point in view.

*distance (int)* - The distance away from the center point to end the pinch. Cannot be less than 1.

*steps (int)* - The amount of touches to generate to complete the pinch out. Cannot be less than 3 and more than 1000.

### Example

```C#
// This will Pinch Out over the center of the UIView and with each finger at 20 pixels from the center of the UIView. The Pinch out action will performed in 100 "touches".
this.ActiveDevice.IOS.PinchOut(Elements.MyScreen9.UIView,null,20,100);
```

```VB
Me.ActiveDevice.IOS.PinchOut(Elements.MyScreen9.UIView,null,20,100)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="ScrollToItem"></a>
## ScrollToItem(IOSQuery[] query, int item, int section, IOSCollectionViewScrollPosition cvScrollPosition)

Scrolls to an item in a section on a view specified by the query.

Supports views and subclasses of: **UICollectionView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*item (int)* - Тhe index of the item to scroll to.

*section (int)* - Тhe section that contains the item to scroll to.

*cvScrollPosition (IOSCollectionViewScrollPosition)* - (enum) the position in the UI the item should scroll to.

### Example

```C#
// This will select an item with index 4 that is part of UICollection
this.ActiveDevice.IOS.SelectItem(Elements.MyScreen2.UICollectionView, 4, 0);
```

```VB
Me.ActiveDevice.IOS.SelectItem(Elements.MyScreen2.UICollectionView, 4, 0)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="ScrollToRow"></a>
## ScrollToRow(IOSQuery[] query, int row, int section, IOSTableViewScrollPosition tvScrollPosition)

Scrolls to a row in a section on a view specified by the query.

Supports views and subclasses of: **UITableView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*row (int)* - Тhe row to scroll to.

*section (int)* - Тhe section that contains the row to scroll to.

*tvScrollPosition (IOSTableViewScrollPosition)* - (enum) The position in the UI the row should scroll to.

### Example

```C#
// This will scroll to row 5, section 0 of UITableView and will make sure that the row will appear as close as possible to the top of the screen
this.ActiveDevice.IOS.ScrollToRow(Elements.MyScreen.UITableView, 5, 0, IOSTableViewScrollPosition.Top);
```

```VB
Me.ActiveDevice.IOS.ScrollToRow(Elements.MyScreen.UITableView, 5, 0, IOSTableViewScrollPosition.Top)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SelectRowInComponent"></a>
## SelectRowInComponent(IOSQuery[] query, int row, int component)

Selects a row in a component of a view specified by the query.

Supports views and subclasses of: **UIPickerView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*row (int)* - The row to select.

*component (int)* - The index of the component that contains the row to select.

### Example

```C#
// Select row 5 from component 0 in the UIPicker 
this.ActiveDevice.IOS.SelectRowInComponent(Elements.MyScreen5.UIPickerView, 5, 0);
```

```VB
Me.ActiveDevice.IOS.SelectRowInComponent(Elements.MyScreen5.UIPickerView, 5, 0)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SelectRow"></a>
## SelectRow(IOSQuery[] query, int row, int section)

Selects a row in a section on a view specified by the query.

Supports views and subclasses of: **UITableView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*row (int)* - The row to select.

*section (int)* - The table view section that contains the row to select.

### Example

```C#
//This will select row 5, section 0 from the UITableView element
this.ActiveDevice.IOS.SelectRow(Elements.MyScreen.UITableView, 5,0);
```

```VB
Me.ActiveDevice.IOS.SelectRow(Elements.MyScreen.UITableView, 5,0)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SelectItem"></a>
## SelectItem(IOSQuery[] query, int item, int section)

Selects an item in a section on a view specified by the query.

Supports views and subclasses of: **UICollectionView**. The item must currently be visible on the screen.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*item (int)* - The index of the item to select.

*section (int)* - The section that contains the item to select.

### Example

```C#
//This will select row 5, section 0 from the UITableView element
this.ActiveDevice.IOS.SelectRow(Elements.MyScreen.UITableView, 5,0);
```

```VB
Me.ActiveDevice.IOS.SelectRow(Elements.MyScreen.UITableView, 5,0)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SetDate"></a>
## SetDate(IOSQuery[] query, DateTime date)

Sets the date on a view specified by the query.

Supports views and subclasses of: **UIDatePicker**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*date (DateTime)* - .NET DateTime object.

### Example

```C#
// This will set the value of a date picker to 2015-12-12 12:00 AM
this.ActiveDevice.IOS.SetDate(Elements.MyScreen3.UIDatePicker, new DateTime(2015, 12, 12));
```

```VB
Me.ActiveDevice.IOS.SetDate(Elements.MyScreen3.UIDatePicker, new DateTime(2015, 12, 12))
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SetText"></a>
## SetText(IOSQuery[] query, string text)

Sets the text on a view specified by the query.

Supports views and subclasses of: **UITextField**, **UITextView**, **UISearchBar**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*text (string)* - The text value to set on the view.

### Example

```C#
// This will set "Set Text" string in the text field
this.ActiveDevice.IOS.SetText(Elements.MyScreen4.UITextField, "Set Text");
```

```VB
Me.ActiveDevice.IOS.SetText(Elements.MyScreen4.UITextField, "Set Text")
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="SetValue"></a>
## SetValue(IOSQuery[] query, double value, int newTimeout = 0)

Sets the value of a view specified by the query.

Supports views and subclasses of **UIStepper**, and **UISlider**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*value (double)* - The value the view should be set to.

*newTimeout (int)* - (optional) An amount of time in milliseconds to wait for the operation to complete.

### Example

```C#
// This will set Value of 0.5 of the UIStepper and fail the operation if it takes more than 100ms
this.ActiveDevice.IOS.SetValue(Elements.MyScreen8.UIStepper, 0.5, 100);
```

```VB
Me.ActiveDevice.IOS.SetValue(Elements.MyScreen8.UIStepper, 0.5, 100)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="Screenshot"></a>
## Screenshot()

Takes a screenshot of the tested UI.

Supports views and subclasses of **UIStepper**, and **UISlider**.

### Return Value

The taken screen shot as array of bytes.

### Example

```C#
// This will make a screenshot of the app under test and return it as an array of bytes
byte[] screenshotInBytes = this.ActiveDevice.IOS.Screenshot();
```

```VB
Dim screenshotInBytes As Byte() = Me.ActiveDevice.IOS.Screenshot()
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="Swipe"></a>
## Swipe(IOSQuery[] query, SwipeDirection direction)

Performs a swipe gesture across the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*direction (SwipeDirection)* - (enum) The direction to swipe.

### Example

```C#
// This will perform a swipe gesture over the UIView to the right
this.ActiveDevice.IOS.Swipe(Elements.MyScreen9.UIView, SwipeDirection.Right);
```

```VB
Me.ActiveDevice.IOS.Swipe(Elements.MyScreen9.UIView, SwipeDirection.Right)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="Tap"></a>
## Tap(IOSQuery[] query, int tapCount = 1, int tapDownDelay = 10, int tapUpDelay = 10)

Performs a tap gesture at the center of the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*tapCount (int)* - (optional) How many times to tap. If null, defaults to 1.

*tapDownDelay (int)* - (optional) The amount of time tap down should last. Defaults to 10 milliseconds and cannot be less.

*tapUpDelay (int)* - (optional) The amount of time tap up should last, if multiple taps are used. Defaults to 10 milliseconds and cannot be less.

### Example

```C#
// This will tap twice UIRoundedRectButton and will use the default value for tapDownDealy and TapUpDelay
this.ActiveDevice.IOS.Tap(Elements.MyScreen1.UIRoundedRectButton, 2);
```

```VB
Me.ActiveDevice.IOS.Tap(Elements.MyScreen1.UIRoundedRectButton, 2)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapAtLocation"></a>
## TapAtLocation(IOSQuery[] query, int x, int y, int tapCount = 1)

Performs a tap gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*x (int)* - The x position to tap in the view.

*y (int)* - The y position to tap in the view.

*tapCount (int)* - (optional) - how many times to tap. If null, defaults to 1.

### Example

```C#
// This will tap twice UIRoundedRectButton at location x=5 and y =10
this.ActiveDevice.IOS.TapAtLocation(Elements.MyScreen1.UIRoundedRectButton, 5, 10, 2);
```

```VB
Me.ActiveDevice.IOS.TapAtLocation(Elements.MyScreen1.UIRoundedRectButton, 5, 10, 2)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapAtPoint"></a>
## TapAtPoint(IOSQuery[] query, TapPoint point = null, int tapCount = 1, int tapDownDelay = 10, int tapUpDelay = 10)

Performs a tap gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*point (TapPoint)* - (optional) The x, y position to tap in the view. If null, defaults to center point in view. If x, or y is negative, that value defaults to the center x, or y of the view.

*tapCount (int)* - (optional) How many times to tap. If null, defaults to 1.

*tapDownDelay (int)* - (optional) The amount of time tap down should last. Defaults to 10 milliseconds and cannot be less.

*tapUpDelay (int)* - (optional) The amount of time tap up should last, if multiple taps are used. Defaults to 10 milliseconds and cannot be less.

### Example

```C#
// This will perform tap on UIbutton on a specific point relative to the button. In this case the point to tap is with x=10 and y=10 offset.
TapPoint point = new TapPoint(10,10);
this.ActiveDevice.IOS.TapAtPoint(Elements.MyScreen1.UIRoundedRectButton, point);
```

```VB
Dim point As New TapPoint(10, 10)
Me.ActiveDevice.IOS.TapAtPoint(Elements.MyScresen1.UIRoundedRectButton, point)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapCenterLeft"></a>
## TapCenterLeft(IOSQuery[] query)

Performs a tap gesture at the center-left of the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

### Example

```C#
//This will will tap exactly at the point between the left end and the exact center of the button
this.ActiveDevice.IOS.TapCenterLeft(Elements.MyScreen1.UIRoundedRectButton);
```

```VB
Me.ActiveDevice.IOS.TapCenterLeft(Elements.MyScreen1.UIRoundedRectButton)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapCenterRight"></a>
## TapCenterRight(IOSQuery[] query)

Performs a tap gesture at the center-right of the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

### Example

```C#
// This will will tap exactly at the point between the right end and the exact center of the button
this.ActiveDevice.IOS.TapCenterRight(Elements.MyScreen1.UIRoundedRectButton);
```

```VB
Me.ActiveDevice.IOS.TapCenterRight(Elements.MyScreen1.UIRoundedRectButton)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapAndHold"></a>
## TapAndHold(IOSQuery[] query)

Performs a tap-and-hold gesture at the center of the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

### Example

```C#
// This will tap the button and hold it tapped for 3 seconds
this.ActiveDevice.IOS.TapAndHold(Elements.MyScreen1.UIRoundedRectButton);
```

```VB
Me.ActiveDevice.IOS.TapAndHold(Elements.MyScreen1.UIRoundedRectButton)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TypeText"></a>
## TypeText(IOSQuery[] query, string text, int keyDelay)

Taps the view specified by the query, then types the specified text using the keyboard.

Supports views and subclasses of **UITextField**, **UITextView**, and **UISearchBar**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*text (string)* - The text value to set on the view.

*keyDelay (int)* - The delay in milliseconds between each key stroke.

### Example

```C#
// This will type "Type Text" string in the text field with 20ms delay between key strokes
this.ActiveDevice.IOS.TypeText(Elements.MyScreen4.UITextField, "Type Text", 20);
```

```VB
Me.ActiveDevice.IOS.TypeText(Elements.MyScreen4.UITextField, "Type Text", 20)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TapSubviewAtIndex"></a>
## TapSubviewAtIndex(IOSQuery[] query, int index)

Taps a subview at an index in the children of a view specified by the query.

Supports views and subclasses of **UISegmentedControl**, **UITabBar**, **UIToolbar**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*index (int)* - The index of the view to tap.

### Example

```C#
// This will tap a subview of index 3 that is child of UIToolbar control
this.ActiveDevice.IOS.TapSubviewAtIndex(Elements.MyScreen6.UIToolbar, 3);
```

```VB
Me.ActiveDevice.IOS.TapSubviewAtIndex(Elements.MyScreen6.UIToolbar, 3)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="Toggle"></a>
## Toggle(IOSQuery[] query, bool toggleValue)

Sets the toggle state of a view specified by the query.

Supports views and subclasses of: **UISwitch**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*toggleValue (bool)* - The on/off true/false state to apply to the togglable view.

### Example

```C#
// Toggles the UISwitch button to true state
this.ActiveDevice.IOS.Toggle(Elements.MyScreen9.UISwitch, true);
```

```VB
Me.ActiveDevice.IOS.Toggle(Elements.MyScreen9.UISwitch, true)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="TwoFingerRotate"></a>
## TwoFingerRotate(IOSQuery[] query, TapPoint point, int angleInDegrees)

Performs a rotate gesture at the specified location within the view specified by the query.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*point (TapPoint)* - The x, y position of origin to rotate around in the view.

*angleInDegrees (int)* - The angle in degrees to rotate.

### Example

```C#
// This will rotate 90 degrees the UIView with two fingers starting from 100 x, 100 y position realtive to the UIView
this.ActiveDevice.IOS.TwoFingerRotate(Elements.MyScreen9.UIView, new TapPoint(100,100), 90);
```

```VB
Me.ActiveDevice.IOS.TwoFingerRotate(Elements.MyScreen9.UIView, new TapPoint(100,100), 90)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="Wait"></a>
## Wait(int miliseconds)

Waits an arbitrary amount of time before continuing execution.

### Parameters

*miliseconds (int)* - The amount of time to wait in milliseconds.

### Example

```C#
// This will pause the execution and will wait for 10ms
this.ActiveDevice.IOS.Wait(10);
```

```VB
Me.ActiveDevice.IOS.Wait(10)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="WaitForElementExists"></a>
## WaitForElementExists(IOSQuery[] query, bool exists, int checkInterval, int timeout)

Executes elementExists command until the result matches the specified value or the timeout occurs.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*exists (bool)* - The expected command value.

*checkInterval (int)* - The interval between elementExists command calls.

*timeout (int)* - The overall number of milliseconds to wait for the element to exist.

### Example

```C#
// This will wait 1000 ms for UISwitch to exists and will check each 10 ms
this.ActiveDevice.IOS.WaitForElementExists(Elements.MyScreen9.UISwitch, true, 10, 1000);
```

```VB
Me.ActiveDevice.IOS.WaitForElementExists(Elements.MyScreen9.UISwitch, true, 10, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="WaitForElementVisible"></a>
## WaitForElementVisible(IOSQuery[] query, bool isVisible, int checkInterval, int timeout)

Executes elementVisible command until the result matches the specified value or the timeout occurs.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*isVisible (bool)* - The expected command value.

*checkInterval (int)* - The interval between elementVisible command calls.

*timeout (int)* - The overall number of milliseconds to wait for the element to get visible.

### Example

```C#
// This will wait 1000 ms for UISwitch to be visible and will check each 10 ms
this.ActiveDevice.IOS.WaitForElementVisible(Elements.MyScreen9.UISwitch, true, 10, 1000);
```

```VB
Me.ActiveDevice.IOS.WaitForElementVisible(Elements.MyScreen9.UISwitch, true, 10, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>

<a id="WaitForPropertyValue"></a>
## WaitForPropertyValue(IOSQuery[] query, string propertyName, string propertyValue, int checkInterval, int timeout)

Executes getPropertyValue command until the result matches the specified value or the timeout occurs.

Supports views and subclasses of: **UIView**.

### Parameters

*query (IOSQuery)* - Identifies an element uniquely.

*propertyName (string)* - The string name of the property.

*propertyValue (string)* - The expected property value as string.

*checkInterval (int)* - The interval between getPropertyValue command calls.

*timeout (int)* - The overall number of milliseconds to wait for the property value to match.

### Example

```C#
// This will wait 1000 ms for UILabel property text to become "test" and will check each 10 ms
this.ActiveDevice.IOS.WaitForPropertyValue(Elements.MyScreen1.UILabel, "text", "test", 10, 1000);
```

```VB
Me.ActiveDevice.IOS.WaitForPropertyValue(Elements.MyScreen1.UILabel, "text", "test", 10, 1000)
```

<a href="#methodsSelect">Back to Top</a>
<br><br>


