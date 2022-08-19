---
title: DOM Explorer Tab
page_title: DOM Explorer Tab
description: "The Test Studio DOM Explorer displays the DOM in a tree or tag format where you see all elements of a page at one time. The Test Studio DOM Explorer is helpful with a complex page when simply using the mouse and hover over highlighting may not be enough to find the element you're looking for"
position: 1
---
# DOM Explorer

The DOM (Document Object Model) is a language neutral and platform independent abstraction that allows the content, structure and style of HTML pages to be updated dynamically. The DOM Explorer displays the DOM in a tree or tag format where you see all elements of a page at one time. The DOM Explorer is helpful with a complex page when simply using the mouse and <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">hover over highlighting</a> may not be enough to find the element you are looking for. The DOM Explorer typically shows the HTML page as the parent element, with *HEAD* and *BODY* elements forming the next level. The elements we are testing are usually within the *BODY* element.

![DOM][1]

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Context Menu

Right click an element to see the context menu and perform several operations against the element.

![Context menu][2]

- **Add to Elements Repository** - adds the selected element to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

- **Goto** - navigate to a parent element. Sample entries include the entire page or an iFrame element within the page.

- **Copy to Clipboard** - copy the DOM element as HTML. Choose either "**Tag Only**" or "**Tag and Children**".

## Toolbar

![Toolbar][3]

1.&nbsp;**Add Element(s)** - you can add single or multiple elements to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>. Click the button to start selecting the elements from the DOM tree. When you are ready to add them to your project, click the **Add Selected** button in the bottom right corner of the **Advanced Recording Tools** window. You can cancel this action by clicking the **Cancel** button.

![Add to Elements][4]

2.&nbsp;**Refresh Elements Tree** - refresh the elements tree of the current application under test in the **Advanced Recording Tools** window. This does not refresh the browser, but only the elements tree that Test Studio uses. Typically used when the elements tree is frozen and there are changes in the DOM tree.

3.&nbsp;**Freeze/Unfreeze Elements Tree** - pause/resume the elements tree auto-refresh option that keeps the elements tree up to date. When in frozen state you can use the refresh elements tree button to update the elements tree.

4.&nbsp;**Search Bar** - search an element in the DOM. You can use the arrow buttons to jump to the next or previous element that matches your search criteria.

> **Tip**
>
> Use # for find expression

5.&nbsp;**Elements Tree and Tag View** - the tree view lists elements in their original hierarchy order and the tag view groups them by their TagName.

6.&nbsp;**Parent Element Filter** - contains entries for the entire page and for iFrame elements within the page. This field is missing if there is only one parent element (i.e. the Page node).

## Searching For Elements

A simple text search may not have enough horsepower to locate elements located deep in a large or complex DOM. For that reason, the DOM Explorer search tool has rich element identification capabilities that range from simple searches by name to complex criteria expressed using XPath and Regular Expression searches. You can use simple find expressions that test an element against a value.

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

> **Note**
>
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

![Hidden][5]

## Regular Expressions

Regular Expressions (RegEx) are sequences of text characters used to describe a search pattern. They are somewhat akin to "wildcard" characters, i.e. "*" or "?", but are much more flexible and powerful. Regular expressions start with the "#" character. See MSDN for examples.

Here is an example that searches for the "onsubmit" attribute that contains the word "myFunction".

![onsubmit][6]

[1]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/dom-explorer/fig6.png
