---
title: DOM Explorer
page_title: DOM Explorer - Test Studio Dev Documentation
description: The DOM explorer in Test Studio Dev displays the DOM in a tree format where you see all elements of a pageat one time. 
slug: recorder/dom
position: 3
---
# DOM Explorer

The DOM (Document Object Model) is a language neutral and platform independent abstraction that allows the content, structure, and style of HTML pages to be updated dynamically. The DOM Explorer in the __Test Studio Dev Recorder__ displays the DOM in a tree format where you see all elements of a page at one time.

![DOM](images/dom-explorer.png)

The DOM Explorer could be quite helpful to explore a complex page when simply using the mouse and hover-over-highlighting may not be enough to find the exact element you're looking for. The DOM Explorer typically shows the HTML page as the parent element, with HEAD and BODY elements forming the next level. The elements we're testing are usually within the BODY element.

## Context Menu

Right click an element to see the context menu and perform several operations against the element.

![Context menu](images/dom-context-menu.png)

- **Add to Elements Repository** - adds the selected element to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

- **Goto** - navigate to a parent element. Sample entries include the entire page or an iFrame element within the page.

- **Copy to Clipboard** - copy the DOM element as HTML. Choose either "**Tag Only**" or "**Tag and Children**".

- **Properties** - show the element's properties in a separate window.

## Toolbar

![Toolbar](images/dom-toolbar.png)

- **Add to Elements** - you can add single or multiple elements to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

![Add to Elements](images/dom-add-element.png)

- **Parent Element Filter** - contains entries for the entire page and for iFrame elements within the page. 

- **Search Tree** - to search an element in the DOM.

- **Elements Tree View** - list elements in their original hierarchy order.

- **Elements Tag View** - group elements by their tag name.

## Searching For Elements

A simple text search may not have enough horsepower to locate elements located deep in a large or complex DOM. For that reason, the DOM Explorer search tool has rich element identification capabilities that range from simple searches by name to complex criteria expressed using XPath and Regular Expression searches. You can use simple find expressions that test an element against a value as shown in the screenshot above. That example shows a hit for an element that has an "id" attribute of "lga".

On the left side of the expression you can use any valid attribute name (i.e. "id", "div", "name", etc.), or any of the following:

- **TextContent** - returns an element that has certain text within it. TextContent is only the text at the same level as the node.

- **InnerText** - looks for text content inside some set of element tags. Inner text is the combined text for a given node and everything below it.

- **InnerMarkup** - returns an element with specific HTML markup inside it.

- **OuterMarkup** - looks for specific HTML markup inclusive of the element itself.

- **StartTagContent**

- **NodeIndexPath**

- **TagName**

- **TagIndex** (zero based)

- **XPath** - XML Path Language expressions, a syntax for selecting elements in an XML document. See MSDN for examples.

> In Silverlight applications you can use Silverlight specific search terms, such as **AutomationId**, **TextContent**, **XamlTag**, and **Name**.

## Operators

Append an additional operator to the "=" to make other comparisons.

~	&nbsp;&nbsp; Contains

!	&nbsp;&nbsp; NotContain

^	&nbsp;&nbsp; StartsWith

?	&nbsp;&nbsp; EndsWith

\#	&nbsp;&nbsp; RegEx

,	&nbsp;&nbsp; And

Here is an example that searches for the "type" attribute that starts with "hidden".

![Search Element](images/dom-search-elements.png)

## Regular Expressions

> Use # for find expression

Regular Expressions (RegEx) are sequences of text characters used to describe a search pattern. They are somewhat akin to "wildcard" characters, i.e. "*" or "?", but are much more flexible and powerful. Regular expressions start with the "#" character. See MSDN for examples.

Here is an example that searches for the "onsubmit" attribute that contains the word "Event".

![Search Element with Regex](images/dom-search-elements-regex.png)