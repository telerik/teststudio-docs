---
title: Demo of Desktop Tests Capabilities
page_title: Demo of Desktop Tests Capabilities
description: "Testing a desktop app with Test Studio. Configure Desktop Test (Standalone) in Test Studio for automating desktop application. Create a Desktop test in Test Studio and record an automated scenario for desktop app. "
position: 4
---
# Demo of Desktop Tests Capabilities

The Desktop testing functionality in Test Studio empowers users to automate the testing of Windows desktop applications. It possesses UI technology independence, meaning it supports various UI technologies such as WPF, WinForms, Delphi, and others. 

This article guides you through a sample scenario and demonstrates the capabilities of Desktop testing in Test Studio: 

* [Prerequisites](#prerequisites)
* [Desktop Testing in Test Studio Explained](#desktop-testing-in-test-studio-explained)
* [The Testing Framework Capabilities and an Example](#the-testing-framework)
* [What is DesktopInvokePattern and an Example](#desktopinvokepattern-example)
* [What are the Automation Properties](#automation-properties)
* [What are the Automation Controls](#automation-controls)
* [What are the Control Patterns](#control-patterns)

## Prerequisites

The only prerequisite for utilizing the Desktop testing capabilities is that the targeted application must implement UI Automation peers. <a href="https://learn.microsoft.com/en-us/windows/apps/design/accessibility/custom-automation-peers" target="_blank">UI Automation peers</a> are a concept within the field of user interface (UI) automation in the context of Microsoft’s UI Automation framework. <a href="https://learn.microsoft.com/en-us/dotnet/framework/ui-automation/ui-automation-overview" target="_blank">UI Automation</a> is an accessibility framework provided by Microsoft that enables software applications to expose their UI elements and interact with them programmatically. 

Each UI element in an application typically has a corresponding UI Automation peer associated with it. Peers encapsulate the accessibility-related information for the elements they represent. They expose properties such as name, control type, keyboard focus, enabled state, and more. 

## Desktop Testing in Test Studio Explained

Test Studio’s desktop testing feature comprises two primary sub-features: the testing framework itself and the Test Studio’s <a href="/automated-tests/recording/overview#desktop-test-recording" target="_blank">recorder and playback functionality</a>. 

### The Testing Framework

The Test Studio Testing framework allows the users to: 

- search UI Automation tree and its elements; 

- read element properties and invoke elements actions ;

- extract element patterns and invoke patterns properties and members; 

- perform keyboard and mouse actions against desktop elements.  

>**Tip**
><br>
><br>
> We recommend using the <a href="https://learn.microsoft.com/en-us/windows/win32/winauto/inspect-objects" target="_blank">Inspect tool</a> when working on coded desktop tests. This tool displays the UI Automation tree and element’s properties in the target application. With the Inspect tool you can explore an element from the application and know how to interact with it.  

### Example

In the following example we use a sample desktop application to locate a radio button within and select it.

![Element in the tested application to locate in code](/img/automated-tests/desktop-testing/demo-desktop-test/1.png)

Launch the Inspect tool and highlight the desired element to reveal its properties. Because of the UI Automation peers enabled we have all the element’s properties exposed. __For building the find expression we will use the name and the class name properties__.

![Inspect tool shows element properties](/img/automated-tests/desktop-testing/demo-desktop-test/2.png)

Make sure you have the following using statements included: 

```C#
    using ArtOfTest.WebAii.DesktopAutomation; 
    using ArtOfTest.WebAii.DesktopAutomation.Controls; 
    using ArtOfTest.WebAii.DesktopAutomation.FindExpressions; 
```

By following the below code flow, users can automate the selection of a radio button within a Windows desktop application using the Test Studio Framework.

```C#
    //The code begins by obtaining the root element of the desktop using ‘DesktopElement.FromDesktopRoot()’. 

    var desktop = DesktopElement.FromDesktopRoot(); 

    //A find expression is created using the name and class name attributes. The expression is defined as follows: 

    var radioButtonExpression = new DesktopFindExpression("name=0", "className=TRadioButton"); 

    //Using the created find expression, the code locates the desired radio button within the desktop: 

    var radioButton = desktop.Find.ByExpression(radioButtonExpression).As<DesktopRadioButton>(); 
    
    //An assertion is then made to ensure that the radio button is not null: 
    Assert.IsNotNull(radioButton); 

    //Finally, the code selects the radio button: 

    radioButton.Select(); 
```

### DesktopInvokePattern Example

Test Studio also provides support for invoking patterns on desktop applications. Here is a general overview of how to use the `DesktopInvokePattern`. The `DesktopInvokePattern` is one of the supported control patterns by Test Studio testing framework. It allows you to invoke an action or command on a UI element in a desktop application. 

Here are the general steps to use the `DesktopInvokePattern` with the radio button from the  above example. 

```C#
    //Find the targer UI element 
    var desktop = DesktopElement.FromDesktopRoot(); 

    var radioButtonExpression = new DesktopFindExpression("name=0", "className=TRadioButton"); 
    var radioButton = desktop.Find.ByExpression(radioButtonExpression); 

    //Retrieve the DesktopInvokePattern 
    var invokePattern = new DesktopInvokePattern(radioButton); 

    //Invoke the desired action 
    invokePattern.Invoke(); 
```

## Automation Properties

__Automation properties are attributes or characteristics associated with user interface elements which provide information about their state, behavior, or appearance__. These properties are used in UI automation for finding and interacting with UI elements programmatically. By accessing these properties, automation tools or frameworks can retrieve information about UI controls, perform actions on them, or make decisions based on their current state. 

Here are few of the commonly used automation properties: 

* __Name__ - The name property represents the accessible name of a UI element. It provides a descriptive name that can be used to find the control. 

* __AutomationId__ - The automation ID property is a unique identifier assigned to a UI element, often set by the application developer explicitly. It allows for reliable identification of controls even if their other properties change. 

* __ControlType__ - The control type property indicates the type or class of the UI element, such as `Button`, `TextBox`, `ComboBox`, or `MenuItem`. It helps in distinguishing between different types of controls. 

* __ClassName__ - The class name property represents the underlying class or control type of a UI element. It can be useful for finding controls based on their implementation details. 

__Full list of supported properties:__

<table class="Tbl k-table">
    <tbody>
        <tr>
            <td style="text-align:left;">AutomationId</td>
            <td style="text-align:left;">ClassName</td>
            <td style="text-align:left;">ControlType</td>
        </tr>
        <tr>
            <td style="text-align:left;">ControlTypeName</td>
            <td style="text-align:left;">Enabled</td>
            <td style="text-align:left;">ExpandCollapse.ExpandCollapseState</td>
        </tr>
        <tr>
            <td style="text-align:left;">IsExpandCollapsePatternAvailable</td>
            <td style="text-align:left;">FrameworkId</td>
            <td style="text-align:left;">Grid.ColumnCount</td>
        </tr>
        <tr>
            <td style="text-align:left;">Grid.RowCount</td>
            <td style="text-align:left;">IsGridPatternAvailable</td>
            <td style="text-align:left;">HasKeyboardFocus</td>
        </tr>
        <tr>
            <td style="text-align:left;">HelpText</td>
            <td style="text-align:left;">IsInvokePatternAvailable</td>
            <td style="text-align:left;">IsKeyboardFocusable</td>
        </tr>
        <tr>
            <td style="text-align:left;">IsLegacyIAccessiblePatternAvailable</td>
            <td style="text-align:left;">LegacyIAccessible.ChildId</td>
            <td style="text-align:left;">LegacyIAccessible.DefaultAction</td>
        </tr>
        <tr>
            <td style="text-align:left;">LegacyIAccessible.Description</td>
            <td style="text-align:left;">LegacyIAccessible.Help</td>
            <td style="text-align:left;">LegacyIAccessible.KeyboardShortcut</td>
        </tr>
        <tr>
            <td style="text-align:left;">LegacyIAccessible.Name</td>
            <td style="text-align:left;">LegacyIAccessible.Role</td>
            <td style="text-align:left;">LegacyIAccessible.State</td>
        </tr>
        <tr>
            <td style="text-align:left;">LegacyIAccessible.Value</td>
            <td style="text-align:left;">LocalizedControlType</td>
            <td style="text-align:left;">Name</td>
        </tr>
        <tr>
            <td style="text-align:left;">ProcessId</td>
            <td style="text-align:left;">IsRangeValuePatternAvailable</td>
            <td style="text-align:left;">RangeValue.IsReadOnly</td>
        </tr>
        <tr>
            <td style="text-align:left;">RangeValue.LargeChange</td>
            <td style="text-align:left;">RangeValue.Minimum</td>
            <td style="text-align:left;">RangeValue.Maximum</td>
        </tr>
        <tr>
            <td style="text-align:left;">RangeValue.SmallChange</td>
            <td style="text-align:left;">RangeValue.Value</td>
            <td style="text-align:left;">RuntimeId</td>
        </tr>
        <tr>
            <td style="text-align:left;">IsSelectionPatternAvailable</td>
            <td style="text-align:left;">Selection.CanSelectMultiple</td>
            <td style="text-align:left;">Selection.IsSelectionRequired</td>
        </tr>
        <tr>
            <td style="text-align:left;">Selection.Selection</td>
            <td style="text-align:left;">IsSelectionItemPatternAvailable</td>
            <td style="text-align:left;">SelectionItem.IsSelected</td>
        </tr>
        <tr>
            <td style="text-align:left;">SelectionItem.SelectionContainer</td>
            <td style="text-align:left;">IsTablePatternAvailable</td>
            <td style="text-align:left;">Table.ColumnHeaders</td>
        </tr>
        <tr>
            <td style="text-align:left;">Table.RowHeaders</td>
            <td style="text-align:left;">Table.RowOrColumnMajor</td>
            <td style="text-align:left;">IsTogglePatternAvailable</td>
        </tr>
        <tr>
            <td style="text-align:left;">Toggle.ToggleState</td>
            <td style="text-align:left;">IsTransformPatternAvailable</td>
            <td style="text-align:left;">Transform.CanMove</td>
        </tr>
        <tr>
            <td style="text-align:left;">Transform.CanResize</td>
            <td style="text-align:left;">Transform.CanRotate</td>
            <td style="text-align:left;">IsValuePatternAvailable</td>
        </tr>
        <tr>
            <td style="text-align:left;">Value.IsReadOnly</td>
            <td style="text-align:left;">Value.Value</td>
            <td style="text-align:left;">IsWindowPatternAvailable</td>
        </tr>
        <tr>
            <td style="text-align:left;">Window.CanMaximize</td>
            <td style="text-align:left;">Window.CanMinimize</td>
            <td style="text-align:left;">Window.WindowInteractionState</td>
        </tr>
        <tr>
            <td style="text-align:left;">Window.IsModal</td>
            <td style="text-align:left;">Window.IsTopmost</td>
            <td style="text-align:left;">Window.WindowVisualState</td>
        </tr>
        <tr>
            <td style="text-align:left;">XPath</td>
            <td style="text-align:left;"></td>
            <td style="text-align:left;"></td>
        </tr>
    </tbody>

</table>

## Automation Controls 
 
__Automation control types categorize different user interface elements based on their functionality and behavior__. These control types help in identifying and distinguishing between various UI controls programmatically. UI automation frameworks and tools use control types to interact with UI elements consistently across different platforms and technologies. 

Here are few of the commonly used UI automation control types: 

* __Button__ - Represents controls that perform an action when clicked, such as buttons, links, or icons. 

* __CheckBox__ - Represents controls that allow users to select or deselect options. 

* __ComboBox__ - Represents controls that provide a dropdown list of options, from which users can select one or more items. 

* __Edit__ - Represents controls that accept and display text input, such as text boxes or input fields. 

__Full list of supported controls:__

<table class="Tbl k-table">
    <tbody>
        <tr>
            <td style="text-align:left;">DesktopButton</td>
            <td style="text-align:left;">DesktopCheckBox</td>
            <td style="text-align:left;">DesktopComboBox</td>
        </tr>
        <tr>
        <td style="text-align:left;">DesktopDataItem</td>
            <td style="text-align:left;">DesktopEdit</td>
            <td style="text-align:left;">DesktopGrid</td>            
        </tr>
        <tr>
            <td style="text-align:left;">DesktopListView</td>
            <td style="text-align:left;">DesktopListViewItem</td>
            <td style="text-align:left;">DesktopProgressBar</td>
        </tr>
        <tr>
            <td style="text-align:left;">DesktopRadioButton</td>
            <td style="text-align:left;">DesktopTab</td>
            <td style="text-align:left;">DesktopTabItem</td>
        </tr>
        <tr>
            <td style="text-align:left;">DesktopText</td>
            <td style="text-align:left;">DesktopTreeView</td>
            <td style="text-align:left;">DesktopTreeViewItem</td>
        </tr>
        <tr>
            <td style="text-align:left;">DesktopWindow</td>
            <td style="text-align:left;"></td>
            <td style="text-align:left;"></td>
        </tr>
    </tbody>

</table>

## Control Patterns
 
__Control patterns refer to a set of standardized behaviors and properties that define the capabilities of a user interface (UI) control__. Control patterns allow automation tools or frameworks to interact with and manipulate UI controls in a consistent and predictable manner. 

Control patterns provide a way to identify and access specific elements within a UI, such as buttons, checkboxes, text boxes, menus, and more. By leveraging control patterns, automation frameworks can perform actions like clicking buttons, entering text, selecting options, and validating the state of UI controls. 

Some commonly used control patterns in UI automation include: 

* __Button Pattern__ - This pattern represents controls that perform an action when clicked, such as buttons, links, or icons. 

* __Edit Pattern__ - This pattern represents controls that accept text input, such as text boxes, input fields, or text areas. 

* __Scroll Pattern__ - This pattern represents controls that allow scrolling through content, such as scroll bars or panning gestures.

__Full list of supported control patterns:__

<table class="Tbl k-table">
    <tbody>
        <tr>
            <td style="text-align:left;">DesktopExpandCollapsePattern</td>
            <td style="text-align:left;">DesktopGridPattern</td>
            <td style="text-align:left;">DesktopInvokePattern</td>
        </tr>
        <tr>
        <td style="text-align:left;">DesktopLegacyIAccessiblePattern</td>
            <td style="text-align:left;">DesktopRangeValuePattern</td>
            <td style="text-align:left;">DesktopSelectionItemPattern</td>            
        </tr>
        <tr>
            <td style="text-align:left;">DesktopSelectionPattern</td>
            <td style="text-align:left;">DesktopTablePattern</td>
            <td style="text-align:left;">DesktopTogglePattern</td>
        </tr>
        <tr>
            <td style="text-align:left;">DesktopTransformPattern</td>
            <td style="text-align:left;">DesktopValuePattern</td>
            <td style="text-align:left;">DesktopWindowPattern</td>
        </tr>
    </tbody>
</table>
