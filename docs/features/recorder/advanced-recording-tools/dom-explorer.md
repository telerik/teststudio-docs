---
title: DOM Explorer Tab
page_title: DOM Explorer Tab
description: "The Test Studio Advanced Recording Tools allow access to the DOM tree of the tested application. The DOM Explorer tab displays the DOM in a tree or tag format where you see all elements of a page at one time. The Test Studio DOM Explorer help with the automation of complex applications when simply using the mouse and hover over highlighting may not be sufficient to find the correct elements."
position: 1
---
# DOM Explorer

The __DOM Explorer__ tab in the __Advanced Recording Tools__ window displays the DOM of the tested application in a tree or tag format. The DOM (Document Object Model) is a language neutral and platform independent abstraction that allows the content, structure and style of HTML pages and desktop applications to be represented dynamically.

![DOM][1]

Find further details about the DOM Explorer functions:

- [Toolbar options](#toolbar-options)
- [Element context menu](#element-context-menu)
- [Searching for elements](#searching-for-elements)
- [Searching with RegEx](#regular-expressions)

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Toolbar Options

The __DOM Explorer__ tab exposes a set of useful functionalities listed in a toolbar. Find out more for each of these in the below list.

- [Add elements](#1-add-elements)
- [Refresh elements](#2-refresh-elements-tree)
- [Freeze/Unfreeze elements tree](#3-freezeunfreeze-elements-tree)
- [Search](#4-search-bar)
- [Tree and Tag View](#5-elements-tree-and-tag-view)
- [Parent element filter](#6-parent-element-filter)

![Toolbar][3]

<h3>1. Add Element(s)</h3>
You can add a single or multiple elements to the project's <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>. Click the button to activate selection and start selecting the elements from the DOM tree. When you are ready to add them to the elements repository, click the **Add Selected** button in the bottom right corner of the *Advanced Recording Tools* window. You can cancel this action by clicking the **Cancel** button.

![Add to Elements][4]

<h3>2. Refresh Elements Tree</h3>
You can manually refresh the elements tree to replicate the current structure of the tested application in the DOM Explorer. This action does not refresh the browser, but only the elements tree that Test Studio recorder uses. Typically used when the elements tree is frozen and there are changes in the DOM tree.

<h3>3. Freeze/Unfreeze Elements Tree</h3>
Test Studio recorder detects any change in the application and automatically refreshes the DOM tree. This option allows you to pause and resume the auto-refresh of the elements tree. This is useful when there is a control on the page, which changes constantly or very often (a countdown watch, for example) and causes the DOM tree to refresh on every second. When in frozen state you can use the [__Refresh Elements Tree__](#refresh-elements-tree) button to update the elements tree manually.

<h3>4. Search Bar</h3>
You can search for an element in the DOM. You can use the arrow buttons to jump to the next or previous element that matches your search criteria.

> **Tip**
>
> Use # for find expression

<h3>5. Elements Tree and Tag View</h3>
The tree view lists elements in their original hierarchy order and the tag view groups them by their TagName.

<h3>6. Parent Element Filter</h3>
This field contains entries for the entire page and for iFrame elements within the page. This field is missing if there is only one parent element (i.e. the Page node).

## Element Context Menu

The __DOM Explorer__ provides few element based options in a context menu. Right click on any element and choose from the available operations.

![Context menu][2]

- **Add to Elements Repository** - adds the selected element to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a> in the project.

- **Goto** - navigate to a parent element. Sample entries include the entire page or an iFrame element within the page.

- **Copy to Clipboard** - copy the DOM element as HTML. Choose either "**Tag Only**" or "**Tag and Children**" depending on what you need to copy - the specific element only or also all its nested elements.

## Searching For Elements

The __DOM Explorer__ allows you to search for elements in the entire DOM tree. A simple text search may not alywas have enough horsepower to locate elements nested deep in a large and complex DOM. For that reason, the __Search Bar__ tool has rich element identification capabilities that range from simple searches by name to complex criteria expressed using XPath and Regular Expression. You can also  use simple find expressions that test an element against a value.

### Search Element Atributes

You can use any valid attribute name (i.e. "id", "div", "name", etc.), or any of the following:

- **TextContent** - returns an element that has certain text within it. TextContent is only the text at the same level as the node.

- **InnerText** - looks for text content inside some set of element tags. Innertext is the combined text for a given node and everything below it.

- **InnerMarkup** - returns an element with specific HTML markup inside it.

- **OuterMarkup** - looks for specific HTML markup inclusive of the element itself.

- **StartTagContent**

- **NodeIndexPath**

- **TagName**

- **TagIndex** (zero based)

- **XPath** - XML Path Language expressions, a syntax for selecting elements in an XML document. See MSDN for examples.

### Search Operators

Append an additional operator to the "=" to make other comparisons.

~	&nbsp;&nbsp; Contains

!	&nbsp;&nbsp; NotContain

^	&nbsp;&nbsp; StartsWith

?	&nbsp;&nbsp; EndsWith

\#	&nbsp;&nbsp; RegEx

,	&nbsp;&nbsp; And

Here is an example that searches for the "type" attribute that contains "hidden".

![Hidden][5]

## Regular Expressions

Regular Expressions (RegEx) are a sequence of text characters used to describe a search pattern. They are somewhat akin to "wildcard" characters, i.e. "*" or "?", but are much more flexible and powerful. Regular expressions in Test Studio start with the "#" character. See <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference" target="_blank">MSDN for examples</a>.

Below picture demonstrates an example that searches for the "onsubmit" attribute that contains the word "myFunction".

![onsubmit][6]

[1]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig6.png
