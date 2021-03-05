---
title: Elements Explorer
page_title: Elements Explorer Overview
description: "Elements Explorer in Test Studio. Elements in the Elements Explorer in Test Studio. Edit an element in Test Studio. Unable to find element failure in Test Studio test"
previous_url: /user-guide/elements-pane-overview.aspx, /user-guide/elements-pane-overview
position: 0
---
# Elements Explorer #

The Elements Explorer in a Test Studio project is the visual representation of all elements recorded or manually added during the <a href="/general-information/test-recording/overview" target="_blank">Test Recording process</a>.

The Elements Explorer pane provides a one-stop shop to view all elements used in the project and edit the way they are found during execution. You can find the Elements Explorer under/next to the Project's Explorer on the left bottom pane.

<table id=no-table>
	<tr>
		<td>![Standalone Version][1] <br><br>**Standalone version**</td>
		<td>![VS Plugin][2] <br><br>**VS plugin**</td>
	</tr>
<table>

> __Tip__
> <br>
> <br>
> Although elements may be used in several tests and test steps, each element with unique find expression is shown only once in the Elements Explorer.

## Hierarchy of Recorded Elements ##

The elements are organized under Page nodes (and also <a href="/general-information/test-recording/frames" target="_blank">Frame nodes</a> if there are frames used in the web page) for web applications and Application and Window Caption nodes for WPF applications.

<table id="no-table">
<tr>
<td>![HTML Tree View][4]<br>**HTML Tree View**</td>
<td>![Silverlight Tree View][5]<br>**Silverlight Tree View**</td>
<td>![WPF Tree View][6]<br> **WPF Tree View**</td>
</tr>
<table>

- The HTML tree view is organized by **Page > Frame > Test Regions > Element**.
- The Silverlight tree view is organized by **Page > Frame > SilverlightApp > Element**.
- The WPF tree view is organized by **Application > Window > Element**.

The hierarchy is maintained according to where the element is located on the page. For example, if there are no frames or regions, then elements for that particular page will be listed under the Page node.

## How to Know Which Step Uses an Element?

Each element in the Elements Explorer is tied to a step from the project. The larger the project gets, the harder it is to sort out which element is used by which step and test. Therefore the Test Studio Elements Explorer provides useful tools to help in maintaining the elements.

- __Which steps use certain element?__ - you can easily check a list of all steps, which uses an element, by accessing the __Used By__ option from the <a href="#element-context-menu" target="_blank">context menu</a>.
- __Can I filter the elements for certain test?__ - with the buttons in the  <a href="#elements-explorer-menu-bar" target="_blank">Elements Explorer menu bar</a>, you can choose what elements to see in the pane.
- __If I select a step in the test, how do I know which element it uses?__ - when a step is selected in the test, its target element gets marked with a red arrow sign in front of its name. The target element is also listed in the <a href="/features/test-maintenance/test-step-properties#elements" target="_blank">step properties</a> under _Primary Target_ property.
- __Can I change the element, which a step uses?__ - the element can be <a href="/features/test-maintenance/change-step-target-element" target="_blank">changed with another existing element by editing the _Primary Target_ step property</a>. Alternatively, you can <a href="/automated-tests/elements/find-element" target="_blank">change the find expression</a> of the element in Test Studio and that way change the element. which will be located on the page.

## Element's Explorer Context Menu ##

### Page Node Context Menu ###

Right click a Page node to see a context menu with these active choices:

![Page Node][7]

- **Validate** - validate all elements in the page node against the currently loaded page. Requires the page to be loaded in the recording window. Results indicated with green checks and red X's. 
- **Rename** - alters the Friendly Name.
- **Load Page** - loads the URL to which the page belongs in the recording window.
- **Properties** - makes the Properties pane active.

### Element Context Menu ###

Each Element node has a context menu with these active choices:

![Elements][8]

- **Edit Element** - loads the Find Element menu to choose where and how to locate this element in your web page or application.
- **Edit in Live** - locate the element in the currently loaded page (available in Test Studio 2018 R3 and earlier).
- **Used By** - loads the Test Step Selector and displays all tests and their steps that contain this element. Selecting one of the listed steps in any test, opens the test in the test pane with the step highlighted.
- **Validate** - validate all elements in the page node against the currently loaded page. Requires the page to be loaded in the recording window. Results indicated with green checks and red X's.
- **Rename** - alters the element's Friendly Name (an easy way to identify the node). This name will also be used for code generation as a variable name or a collection indexer.
- **Delete** - remove the element from the Explorer. The element must be linked to no steps.
- **View Error** - show the erroneous find logic for an element that cannot be found.
- **Locate in DOM** - jump to this element's position in the DOM when the recording window is loaded.
- **Load Page** - loads the URL to which the element belongs in the recording window.
- **Properties** - makes the Properties pane active.

## Element's Explorer Menu Bar ##

The Elements menu bar ![Elements bar][3] has the following buttons:

- **Add Element** - add a <a href="/features/elements-explorer/predefined-elements" target="_blank">Predefined element</a>.
- **Element Mapping (IntelliMap)** - <a href="/features/elements-explorer/element-mapping" target="_blank">Map</a> a Predefined element.
- **Search** - search the Explorer based on the element Friendly Name property.
- **Sort** - organize the elements in an ascending or descending order, or clear the sorting.
- **Refresh** - refresh the display of elements in the Explorer. You seldom should have to do this because Test Studio  normally refreshes the window properly.
- **Enable/Disable Highlighting** - control the highlighting of elements on the recording surface as they are selected in the tree view. When enabled, an element highlighted in the Elements pane will also be highlighted in the active browser.
- **Expand/Collapse** - show or hide all elements under their respective page nodes.
- **This Test/All Tests** - show elements for the currently loaded test only, or the elements for every test in the project.

[1]: /img/features/elements-explorer/overview/fig1.png
[2]: /img/features/elements-explorer/overview/fig2.png
[3]: /img/features/elements-explorer/overview/fig3.png
[4]: /img/features/elements-explorer/overview/fig4.png
[5]: /img/features/elements-explorer/overview/fig5.png
[6]: /img/features/elements-explorer/overview/fig6.png
[7]: /img/features/elements-explorer/overview/fig7.png
[8]: /img/features/elements-explorer/overview/fig8.png