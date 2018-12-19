---
title: Overview
page_title: Elements Explorer Overview
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/elements-pane-overview.aspx, /user-guide/elements-pane-overview
position: 0
---
# Elements Explorer

The Elements Explorer is similar to the DOM Explorer in that it displays a tree of elements, but the Elements Explorer only contains elements you want to use in your tests. Also, the elements in the tree view have properties that are more specific to testing. Although elements may be used in several tests and test steps, each element is shown only once in the Elements Explorer.

You can find the Elements Explorer under the Elements tab on the left bottom pane.

![Standalone Version][1]

**Standalone Version**

![VS Plugin][2]

**VS Plugin**

The Elements tab, maintains a list of all Elements within the current project. It provides a one-stop shop to view elements and edit the way they are found during execution. 

The Elements menu bar ![Elements bar][3] has the following buttons:

- **Add Element** - add a <a href="/features/elements-explorer/predefined-elements" target="_blank">Predefined element</a>.
- **Element Mapping (IntelliMap)** - <a href="/features/elements-explorer/element-mapping" target="_blank">Map</a> a Predefined element.
- **Search** - search the Explorer based on the element Friendly Name property.
- **Sort** - organize the elements in an ascending or descending order, or clear the sorting.
- **Refresh** - refresh the display of elements in the Explorer. You seldom should have to do this because Test Studio  normally refreshes the window properly.
- **Enable/Disable Highlighting** - control the highlighting of elements on the recording surface as they are selected in the tree view. When enabled, an element highlighted in the Elements pane will also be highlighted in the active browser.
- **Expand/Collapse** - show or hide all elements under their respective page nodes.
- **This Test/All Tests** - show elements for the currently loaded test only, or the elements for every test in the project.

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

Right click a Page node to see a context menu with these active choices:

![Elements][7]

- **Validate** - validate all elements in the page node against the currently loaded page. Requires the page to be loaded in the recording window. Results indicated with green checks and red X's. 
- **Rename** - alters the Friendly Name.
- **Load Page** - loads the URL to which the page belongs in the recording window.
- **Properties** - makes the Properties pane active. 

Each Element node has a context menu with these active choices:

![Elements][8]

- **Edit Element** - loads the Find Element menu to choose where and how to locate this element in your web page or application.
- **Edit in Live** - locate the element in the currently loaded page.
- **Used By** - loads the Test Step Selector and displays all tests and their steps that contain this element.
- **Validate** - validate all elements in the page node against the currently loaded page. Requires the page to be loaded in the recording window. Results indicated with green checks and red X's.
- **Rename** - alters the element's Friendly Name (an easy way to identify the node). This name will also be used for code generation as a variable name or a collection indexer.
- **Delete** - remove the element from the Explorer. The element must be linked to no steps.
- **View Error** - show the erroneous find logic for an element that cannot be found.
- **Locate in DOM** - jump to this element's position in the DOM when the recording window is loaded.
- **Load Page** - loads the URL to which the element belongs in the recording window.
- **Properties** - makes the Properties pane active. 

[1]: /img/features/elements-explorer/overview/fig1.png
[2]: /img/features/elements-explorer/overview/fig2.png
[3]: /img/features/elements-explorer/overview/fig3.png
[4]: /img/features/elements-explorer/overview/fig4.png
[5]: /img/features/elements-explorer/overview/fig5.png
[6]: /img/features/elements-explorer/overview/fig6.png
[7]: /img/features/elements-explorer/overview/fig7.png
[8]: /img/features/elements-explorer/overview/fig8.png