---
title: Test Step Properties
page_title: Test Step Properties - Test Studio Dev Documentation
description: Test step properties in Test Studio Dev 
slug: features/test-step-properties
position: 1
---
# Test Step Properties

To view the properties for a __Test Studio Dev__ test step make sure the Properties pane in Visual Studio is visible in the lower right - click **View > Properties Window** or press the F4 key. Then click on any step in the test to visualize its properties in the pane. By default all test step properties are listed alphabetically. Click the Categorized icon to add headings and categorize the list.

![Properties VS][2]

The step properties are context based as of the selected step type. Highlight any property for a description of what it does and how it affects your test. Below is a list of all properties across the different step types. 

## Behavior

<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
}
table.docs th {
color:#fff;
background-color:#00аб8е;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}

</style>
<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**AltKey**</td><td>Whether to hold the Alt key while clicking.</td><td>To execute an Alt + Click.</td>
</tr>
<tr>
<td>
	
**AnnotationText**</td><td>The text to use for annotation.</td><td>With a Custom Annotation step.</td>
</tr>
<tr>
<td>
	
**BaseUrl**</td><td>The BaseURL to use when a global base is missing.</td><td> </td>
</tr>
<tr>
<td>
	
**CaptureType**</td><td>The type of window to capture.</td><td>With a Browser/Desktop Capture step.</td>
</tr>
<tr>
<td>
	
**ClickPoint / Offset**</td><td>ClickUnitType - the unit of point to use: percentage or pixel.<br>OffSetReference - the reference point of screen to use for the click.<br>X - the x-axis offset from reference point.<br>Y - the y-axis offset from reference point.</td><td>To click the target element based on specific offset coordinates instead of at absolute center.</td>
</tr>
<tr>
<td>
	
**ClosesBrowser**</td><td>ndicates to the automation that this action will force the browser to close. Typical for HTML pop-ups.</td><td>With a Click step that closes an HTML pop-up.</td>
</tr>
<tr>
<td>
	
**ControlKey**</td><td>Whether to hold the <em>Ctrl</em> key while clicking.</td><td>To execute a Ctrl + Click. </td>
</tr>
<tr>
<td>
	
**Desktop Command Type**</td><td> The mouse action type.</td><td></td>
</tr>
<tr>
<td>
	
**DisplayLocation**</td><td>The location to display the annotation relative to the browser window.</td><td>With a Custom Annotation step.</td>
</tr>
<tr>
<td>
	
**DisplayTime**</td><td> The length of time in milliseconds to display the annotation.</td><td>With a Custom Annotation step.</td>
</tr>
<tr>
<td>
	
**Encrypt**</td><td>When set, will encrypt text typed into input control.<br>Once set to true, cannot be changed back to false.<br>'Text' property cannot be modified and current step cannot be converted to code. </td><td>With a <em>Set text</em> step on a password field. </td>
</tr>
<tr>
<td>
	
**EventType**</td><td>The Javascript event type to invoke.</td><td></td>
</tr>
<tr>
<td>
	
**FileNamePrefix**</td><td>The file name prefix to use to save the capture on disk.</td><td>To edit the file name for a browser or desktop Capture image.</td>
</tr>
<tr>
<td>
	
**FireKeyEvents**</td><td>Whether to fire <em>KeyDown</em> and <em>KeyUp</em> events during simulated typing.</td><td>If target input element requires these events to be fired.</td>
</tr>
<tr>
<td>
	
**Focus**</td><td>Scroll element into view before performing an action on it.</td><td>For action steps that require the element be scrolled into view before being acted upon.</td>
</tr>
<tr>
<td>
	
**HandleButton**</td><td>The button to click to handle this dialog.</td><td>To change the button clicked in the dialog.</td>
</tr>
<tr>
<td>
	
**HandleTimeout**</td><td>The timeout in milliseconds for the dialog to be handled once it is detected.</td><td>Increase if dialog is not fully handled within time set.</td>
</tr>
<tr>
<td>
	
**InitializationTime**</td><td>The fixed time to wait in milliseconds before the handling of the dialog starts.</td><td>Increase if dialog needs longer to initialize.</td>
</tr>
<tr>
<td>
	
**IsPassword**</td><td>Whether the text field is a password.</td><td>To mask the password in the step description. </td>
</tr>
<tr>
<td>
	
**KeyHoldTime**</td><td>The length of time in milliseconds to hold each key down when <em>SimulateRealTyping</em> is true.</td><td>To slow down or speed up typing.</td>
</tr>
<tr>
<td>
	
**Modifier Keys**</td><td>Any modifier keys held while clicking.</td><td>If the click step requires a modifier key to be held.</td>
</tr>
<tr>
<td>
	
**MouseButton**</td><td>The clicked mouse button.</td><td>With a Mouse Action Desktop Command step.</td>
</tr>
<tr>
<td>
	
**NavigateUrl**</td><td>The URL for the Navigate step.</td><td>To edit the target URL.</td>
</tr>
<tr>
<td>
	
**OverrideFile**</td><td>Whether to override the image file if it exists.</td><td>To create new or override existing browser or desktop Capture images.</td>
</tr>
<tr>
<td>
	
**Recorded Text Content**</td><td> Text to use when <em>SimulateRealTyping</em> is false.</td><td>To edit input text.</td>
</tr>
<tr>
<td>
	
**ScrollToVisibleType**</td><td>Scroll element to visible type.</td><td>To set a Scroll step to window top, center or bottom.</td>
</tr>
<tr>
<td>
	
**SearchByImageFirst**</td><td>Search by image before searching by element's find expression.</td>
**ParentSetting** will inherit Project or Test List settings. **True** and **False** overrides Project and Test List settings.</td>
</tr>
<tr>
<td>
	
**ShiftKey**</td><td>Whether to hold the Shift key while clicking.</td><td>To execute a Shift + Click.</td>
</tr>
<tr>
<td>
	
**SimulateRealClick**</td><td>Whether to perform the click using the mouse rather than directly invoking a click on the DOM element.</td><td>If the click target requires a real click to trigger an event or validation.</td>
</tr>
<tr>
<td>
	
**SimulateRealTyping**</td><td>Whether to simulate real text typing one character at a time.</td><td>If input field requires real typing to trigger an event or validation.</td>
</tr>
<tr>
<td>
	
**SimulateRealUser**</td><td>Whether to simulate real user actions.</td><td>For Silverlight/WPF action steps.</td>
</tr>
<tr>
<td>
	
**Text**</td><td>Text entered into input control.</td><td>To edit the input text.</td>
</tr>
<tr>
<td>
	
**TimeBetweenKeyPresses**</td><td>The pause in milliseconds between key presses to use when SimulateRealUser is set.</td><td>To increase or decrease the typing speed.</td>
</tr>
<tr>
<td>
	
**Typed Text**</td><td>Text that will be played back when <em>SimulateRealUser</em> is true.</td><td>To edit the typed text.</td>
</tr>
<tr>
<td>
	
**Typing Delay**</td><td>The pause between key presses when <em>SimulateRealUser</em> is set.</td><td>To increase or decrease the typing speed. </td>
</tr>
<tr>
<td>
	
**Use Offset**</td><td>Whether to click at a specific point within the target element or the center of it.</td><td>With a Click step. </td>
</tr>
<tr>
<td>
	
**WaitTime**</td><td>Time to wait in milliseconds.</td><td>With an Execution Delay step. </td>
</tr>
<table>

## Comment

<table class="docs">
<tr>
	<th>Property</th><th>Property</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**Comment**</td><td>The text comment to display as a single test step in the test log.</td><td>To insert a comment into the test log next to the step. </td>
</tr>
<table>

## Data Driven

<table class="docs">
<tr>
	<th>Property</th><th>Property</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**(Bindings)**</td><td>Bind data driven properties against a data source. Click the drop-down to see properties that support data binding.</td><td>To data bind the step to a specific column from the data source.</td>
</tr>
<table>

## Dialog Identification

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**ChildWindowTextContent**</td><td>A partial text that might be found on the dialog.</td><td>If two dialogs have similar titles, further distinguish them by adding this property. </td>
</tr>
<tr>
<td>
	
**DialogTitle**</td><td>The dialog title to look for to identify the dialog.</td><td>To edit the identifying dialog title. </td>
</tr>
<tr>
<td>
	
**MatchPartialTitle**</td><td>Whether to use partial text matching to match the dialog title.</td><td>To match an exact or partial dialog title. </td>
</tr>
<table>

## Download

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**DownloadPath**</td><td>The download location to set for the download dialog.</td><td>To change where a file is saved by the Download dialog handler step. </td>
</tr>
<table>

## Drag Settings

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**Offset**</td><td>ClickUnitType - the unit of point to use: percentage or pixel.<br>OffSetReference - the reference point of screen to use for the click.<br>X - the x-axis offset from reference point.<br>Y - the y-axis offset from reference point.</td><td>To start the drag from an offset of the source element, as opposed to absolute center. </td>
</tr>
<table>

## Drop Settings

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**DragDropWindowData**</td><td>Used when entire window is considered the drop target.</td><td>To edit the window coordinates where the source element is dropped when using window target.</td>
</tr>
<tr>
<td>
	
**DropOffset**</td><td>The offset to use for the drop target.</td><td>To drop the source element to offset coordinates of the target element. </td>
</tr>
<tr>
<td>
	
**DropTargetType**</td><td>The type of drop target to use for the drag drop.</td><td>To drop the source element to a window or element target. Element targets tend to be more reliable. </td>
</tr>
<table>

## Elements

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**Drag Element**</td><td>Key of the element to use for the drag.</td><td>To change the source element to drag. </td>
</tr>
<tr>
<td>
	
**Drop Element**</td><td>Key of the element to use for the drop.</td><td>To change the target element to drop onto. </td>
</tr>
<tr>
<td>
	
**PrimaryTarget**</td><td>The primary automation element that this step is targeting.</td><td>To change the element the step is based on. </td>
</tr>
<tr>
<td>
	
**SecondaryTarget**</td><td>The primary automation element that this step is targeting. Used only for steps that require two targets, like a drag and drop.</td><td>Only in drag and drop scenarios. </td>
</tr>
<tr>
<td>
	
**Virtualizing Container**</td><td>The object containing this element, if any.</td><td>(Silverlight only) </td>
</tr>
<tr>
<td>
	
**Virtualizing Container Offset**</td><td>The offset to scroll the virtualizing container to before searching for the target element of this step.</td><td>(Silverlight only) </td>
</tr>
<table>

## Execution

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**AjaxTimeout** </td><td>The timeout to wait for pending AJAX requests. </td><td>If the test step relies on an AJAX postback to complete before proceeding. </td>
</tr>
<tr>
<td>
	
**EnsureElementsClickable**</td><td>Whether to ensure the target element of this action is visible and clickable before performing the action.</td><td></td>
</tr>
<tr>
<td>
	
**ScrollToVisibleType**</td><td>When 'SimulateRealClick' or 'SimulateRealTyping' is set to 'True', you can specify the scroll direction in order to get the target element into view.</td><td>Choose whether to scroll the element to top, center or  bottom of the page.</td>
</tr>
<tr>
<td>
	
**Pause**</td><td>Whether to pause the step during execution. Only respected when running tests from the Test Explorer.</td><td>To pause test execution at a certain point to manually debug. </td>
</tr>
<tr>
<td>
	
**UseStepWaitOnElementsTimeout**</td><td>Whether to use step's WaitOnElementsTimeout instead of the global setting.</td><td>To specifically increase one step's element locating timeout. </td>
</tr>
<tr>
<td>
	
**WaitForNoMotion**</td><td>Wait for the element to stop moving before executing the action.</td><td></td>
</tr>
<tr>
<td>
	
**WaitOnElements**</td><td>Whether to wait on step's elements to exist before executing it.</td><td>The default is True (recommended). False will ignore the Global and per step settings and will execute the step without waiting for the element (not recommended). </td>
</tr>
<tr>
<td>
	
**WaitOnElementsTimeout**</td><td>Number of milliseconds to wait for element to exist if <em>WaitOnElements</em> is true.</td><td>To specifically increase one step's element locating timeout. </td>
</tr>
<table>

## Extraction

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**DataBindVariableName**</td><td>The name with which this extraction is published.</td><td>To change the Extraction variable used for later data binding. </td>
</tr>
<table>

## jQuery

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**TriggerjQueryEvent**</td><td>During step execution, attempt to trigger proper jQuery event.</td><td>Step is expected to trigger a jQuery event on the page.</td>
</tr>
<table>

## Handle Button

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**ButtonId**</td><td>The button ID to use when <em>HandleButtonMethod = ButtonId</em>.</td><td>To edit the button ID used to handle a Generic dialog. </td>
</tr>
<tr>
<td>
	
**ButtonPartialText**</td><td>The partial button text to use when <em>HandleButtonMethod = ButtonPartialText</em>.</td><td>To edit the partial button text used to handle a Generic dialog. </td>
</tr>
<tr>
<td>
	
**HandleButtonMethod**</td><td>Identification method of the handle method. <em>NoneCloseDialog</em> simply attempts to knock down the dialog using the Close button.</td><td>To change the handle method for a Generic dialog.</td>
</tr>
<table>

## Logon

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**Password**</td><td>The password to use to log on.</td><td>To edit the password in a Logon dialog handler step. </td>
</tr>
<tr>
<td>
	
**UserName**</td><td>The user name to use to log on.</td><td>To edit the user name in a Logon dialog handler step. </td>
</tr>
<table>

## Manual Properties

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**ExecutionTimeout**</td><td>Timeout in milliseconds to wait for the manual execution, else step will timeout and log a failure.</td><td>To change the time in minutes a Manual step will wait for input. </td>
</tr>
<tr>
<td>
	
**ManualDescription**</td><td>Description displayed in <em>Execute Manual Step</em> dialog.</td><td>To edit the message displayed in the Manual step dialog. </td>
</tr>
<table>

## Misc

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**DialogType**</td><td>The type of dialog handled by the step.</td><td>(Read only) </td>
</tr>
<tr>
<td>
	
**InvokeSelectionChanged** </td><td>Whether to invoke the OnChange javascript event. </td><td>If the step requires the OnChange event. </td>
</tr>
<tr>
<td>
	
**IsDoubleClick**</td><td>Whether a click step is a single or double click.</td><td>To toggle between single or double click. </td>
</tr>
<tr>
<td>
	
**IsPartial**</td><td>Whether to perform a partial or exact match on the URL.</td><td>With a Wait For Url step. </td>
</tr>
<tr>
<td>
	
**LogMessageOnFailure**</td><td>Message to log as part of log content if step fails.</td><td>To insert a custom message in the test log if the step fails. </td>
</tr>
<tr>
<td>
	
**RequiresSilverlight**</td><td>Whether this step requires Silverlight to be enabled.</td><td></td>
</tr>
<tr>
<td>
	
**RunsAgainst**</td><td>The browsers this step can run against.</td><td>If a step should only be run for a specific browser type. </td>
</tr>
<tr>
<td>
	
**RunsAgainstVersion**</td><td>The browser version that this step can run against.</td><td>If a step should only be run for a specific browser version. </td>
</tr>
<tr>
<td>
	
**RunsAgainstVersionCompare**</td><td>The compare type of the browser version that this step can run against.</td><td>To change the browser version comparison from Equals to LessThan, for example.</td>
</tr>
<tr>
<td>
	
**StepType**</td><td>Step descriptor type.</td><td>(Read only) </td>
</tr>
<tr>
<td>
	
**TestName**</td><td>Name of the test to execute for Test as Step.</td><td>(Read only) </td>
</tr>
<tr>
<td>
	
**TestPath**</td><td>Test path to use for Test as Step.</td><td></td>
</tr>
<tr>
<td>
	
**TestUniqueId**</td><td>Unique ID for Test as Step.</td><td></td>
</tr>
<tr>
<td>
	
**Url**</td><td>The URL to wait for.</td><td>With a Wait For Url step. </td>
</tr>
<tr>
<td>
	
**WaitTimeout**</td><td>The timeout to use for waiting.</td><td>With a Wait For Url step.</td>
</tr>
<table>

## Upload

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**FileUploadPath**</td><td>The file upload path on disk.</td><td>To change the upload path. </td>
</tr>
<table>

## Verification

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**AttributeName** </td><td>The attribute name to verify. </td><td>To change the target attribute to verify. </td>
</tr>
<tr>
<td>
	
**AttributeValue** </td><td>The attribute value to verify. </td><td>To change the attribute's value to verify. </td>
</tr>
<tr>
<td>
	
**CompareType**</td><td>The compare type of the text verification.</td><td>To change from an exact to a partial match, for example. </td>
</tr>
<tr>
<td>
	
**EnsureStateIsCurrent**</td><td>Whether to explicitly refresh the target element on which the verification is performed.</td><td>To eliminate the need to explicitly refresh the DOM tree in a coded step before the verification. </td>
</tr>
<tr>
<td>
	
**ExpectedString**</td><td>The expected string to compare against.</td><td>To change the string to verify. </td>
</tr>
<tr>
<td>
	
**PropertyName**</td><td>The name of the property being verified.</td><td>To change the property to verify. </td>
</tr>
<tr>
<td>
	
**TagSegmentType**</td><td>The segment of the target element to compare.</td><td>To change which attribute the Verification is based on. </td>
</tr>
<tr>
<td>
	
**Value**</td><td>Represents the expected value of the property.</td><td>To change the value to verify. </td>
</tr>
<table>

## Wait

<table class="docs">
<tr>
	<th>Property</th><th>Description</th><th>When To Use</th>
</tr>
<tr>
<td>
	
**CheckInterval**</td><td>The check interval in milliseconds when acting as a Wait.</td><td>To cause the Wait to check its condition more or less frequently.</td>
</tr>
<tr>
<td>
	
**IsWaitOnly**</td><td>Whether this descriptor can only be a wait.</td><td>(Read only)</td>
</tr>
<tr>
<td>
	
**SupportsWait**</td><td>Whether this verification supports wait.</td><td>(Read only)</td>
</tr>
<tr>
<td>
	
**Timeout**</td><td>The wait time when acting as a wait.</td><td>To increase or decrease the wait time. </td>
</tr>
<table>


[2]: images/test-step-properties/fig2.png
