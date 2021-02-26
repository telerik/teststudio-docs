---
title: Elements Find Expression
page_title: Elements Find Expression
description: "How elements get recorded in a test Studio test. Find Expressions in Test Studio. How an element is being located during test execution. What is find expression, how is find expression build for elements in Test Studio tests"
position: 0
---
# Elements Find Expression

The Element Find Expression in Test Studio is a set of unique identifiers for an element from the tested application, which are used to locate the element in test run-time.

When recording any action against a control from a web page or WPF application, Test Studio adds an element related to the step and generates a **Find Expression** for that element. The same process is triggered, if an <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">element is explicitly added</a> to the Elements repository from the DOM explorer.

## How is Element's Find Expression Generated?

#### Test Studio records steps and adds elements out-of-the-box, but what criteria it uses to generate unique find expressions for the elements?

Test Studio uses a predefined set of criteria to look for in the attributes of an element - based on the <a href="/features/project-settings/find-logic" target="_blank">order for the attributes to use</a>, Test Studio detects the most appropriate combination of find clauses to identify the elements in the application and generates a find expression.

> __Tip__
> <br>
> <br>
> The __order of attributes to be used, when recording HTML elements, can be reordered and customized__. If the application under test uses custom tags, which are unique for the elements, you can add it and set it on the first position.

#### Test Studio adds image for each recorded element. Can I use only the images to locate elements when running my tests?

The recorded images for each element in Test Studio can be used as a default identification mechanism for a project. The <a href="/features/project-settings/find-logic" target="_blank">find logic settings</a> allow you to enable the usage of images before searching for the element with its find expression.

## Element's Attributes Used in the Find Expressions

The basic component of elements' **Find Expressions** in Test Studio is the __FindClause - this is a _name-value_ pair connected with a comparison operator__. The Find Expression consists of at least one FindClause and this can be verified when <a href="/features/elements-explorer/find-element" target="_blank">editing the element</a>.

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

> **Note**
> <br>
> <br>
> When <a href="/features/elements-explorer/find-element#options-in-element-pane-with-active-recording-session" target="_blank">editing an element in active recording session</a>, all available element's properties are listed for direct selection in the Find Expression Builder.
> ![Element's attributes][3]

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

> **Note**
> <br>
> <br>
> Switching the *Elements Edit pane* to modify the image settings or to record new image, __requires to save any current changes__ in the same element's Find Expression.

## Basic Concept

The main idea, when choosing the proper FindClauses and what comparison to apply, is to build a find expression, which points uniquely to a single element in the active application. Test Studio analyze the DOM tree and the structure of elements in it and strives to generate a unique find expression based on the current DOM tree.

- For HTML application Test Studio relies on the <a href="/features/project-settings/find-logic" target="_blank">**Find Logic criteria**</a> list and its particular order. This can be adjusted on project level.

- For hierarchical controls such as TreeViews, Test Studio creates <a href="/knowledge-base/project-configuration-kb/using-chained-find-expressions" target="_blank">**chained find expressions**</a>.

- Use unique elements' attributes, which are not dynamically generated to ensure a single element in the application will be pointed by this find expression.

[1]: /img/features/elements-explorer/element-find-expression/fig1.png
[2]: /img/features/elements-explorer/element-find-expression/fig2.png
[3]: /img/features/elements-explorer/element-find-expression/fig3.png