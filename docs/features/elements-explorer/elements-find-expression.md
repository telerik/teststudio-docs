---
title: Elements Find Expression
page_title: Elements Find Expression
description: "How elements get recorded in a test Studio test. Find Expressions in Test Studio. How an element is being located during test execution. What is find expression, how is find expression build for elements in Test Studio tests"
position: 1
---
# Elements Find Expression

When an action is recorded against an element from a web page or WPF application, Test Studio generates a **Find Expression**, which is then used to locate that element in the application during execution. The same process is triggered if an element is explicitly added to the Elements repository from the DOM explorer.

## FindClauses

The basic component of elements' **Find Expressions** in Test Studio is the FindClause - this is a name-value pair connected with a comparison operator. The Find Expression consists of at least one FindClause and this can be verified when <a href="/features/elements-explorer/find-element" target="_blank">editing the element</a>.

![Element's find expression][1]

The *'name'* portion of a FindClause pair can be any element's property that a certain technology (i.e. HTML, XAML) recognizes.

### HTML Find Expression

- Any valid attribute name (id, name, etc.)

- TextContent - search for an element in which has text that matches the specified expression.

- InnerText - search for an element in which the InnerText matches the specified expression.

- InnerMarkup - search for an element in which the InnerMarkup matches the specified expression.

- OuterMarkup - search for an element in which the OuterMarkup matches the specified expression.

- StartTagContent - search for an element in which the StartTagContent matches the specified expression.

- NodeIndexPath - search for an element having the specified NodeIndexPath.

- TagName - search for an element in which the TagName matches the specified expression.

- TagIndex - search for an element at the specified zero based TagIndex.

- XPath - search for an element at the specified XPath expression.

### XAML Find Expression

- AutomationId - search for an element having an automation ID of a specific value.

- TextContent - search for an element containing or not containing some text.

- XamlTag - search for an element of a specific type.

- XamlTagBase - search for an element that extends a specific type

- Name - search for an element having a name of a specific value.

- TagIndex - the zero based index value of a specific tag.

- XamlPath - Uses a XAML path expression like XamlPath=/radtabcontrol[automationid=Tabs]/grid[0]/raddockpanel[0]/layouttransformcontrol[name=HeaderDockedElement]

> **Note:** When <a href="/features/elements-explorer/find-element#options-in-element-pane-with-active-recording-session" target="_blank">editing an element in active recording session</a>, all available element's properties will be listed and available for direct selection in the Find Expression.

![Element's attributes][3]

### Comparison Operators

The available comparison operators for each FindClause are: *'is exactly'*, *'contains'*, *'does not contain'*, *'starts with'*, *'ends with'*,
*'matches the regular expression'*, *'is missing'* and *'exists'*.

![FindClause comparison operators][2]

## Element's Image

The find expression of elements in Test Studio is also enhanced with corresponding images - each recorded element gets an image recorded along with its automatically generated find expression. The image will be used as a backup search criteria in case the element's find clauses didn't match any element on the page.

### Conditions to Fall Back to Find Elements by Image

The test execution flow remains unchanged. The enhancement is that when an element fails to be located on page with its find expression within the set [Elements Timeout](/general-information/test-execution/quick-execution#execution-timeouts), Test Studio automatically falls back to the element image search and continues as expected if the element is found using the predefined image. The execution results contain warning that the element's find expression didn't match any element on page and it was found by image.

### Modifying the Predefined Image

The recorded <a href="/features/elements-explorer/find-element-by-image" target="_blank">image for each element can be edited</a> separately from the find expression.

> **Note:** Switching the *Elements Edit pane* to modify the image settings or recording new image, requires to save any current changes in the same element's Find Expression.

## Basic Concept

The main idea, when choosing the proper FindClauses and what comparison to apply, is to build a find expression, which points uniquely to a single element in the active application. Test Studio analyze the DOM tree and the structure of elements in it and strives to generate a unique find expression based on the current DOM tree.

- For HTML application Test Studio relies on the <a href="/features/project-settings/find-logic" target="_blank">**Find Logic criteria**</a> list and its particular order. This can be adjusted on project level.

- For hierarchical controls such as TreeViews, Test Studio creates <a href="/knowledge-base/project-configuration-kb/using-chained-find-expressions" target="_blank">**chained find expressions**</a>.

- Use unique elements' attributes, which are not dynamically generated to ensure a single element in the application will be pointed by this find expression.

[1]: /img/features/elements-explorer/element-find-expression/fig1.png
[2]: /img/features/elements-explorer/element-find-expression/fig2.png
[3]: /img/features/elements-explorer/element-find-expression/fig3.png