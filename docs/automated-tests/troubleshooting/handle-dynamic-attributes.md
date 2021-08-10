---
title: How to Handle Elements with Dynamic Attributes
page_title: How to Handle Elements with Dynamic Attributes?
description: "How to improve elements recording if all elements have dynamic ids. My tests are constantly failing with element not found errors. How can I choose more robust find expressions for the elements. " 
position: 5
---
# How to Handle Elements with Dynamic Attributes

Modern web applications often generate dynamic attributes for the HTML elements. This is often a significant challenge for test automation tools. Test Studio provides built-in capabilities to ease the automatic recording of elements for such pages and their long-term maintenance.

This article will guide you through the handy features, which can ease you when automating a web application whose elements have dynamic attributes.

## Record the Scenario

In this tutorial, we use a sample application. The task is to click the button and verify that the text in the paragraph is changed after the click.

![Sample web app](/img/automated-tests/troubleshooting/handle-dynamic-attributes/1Showcase.png)

We’ve already launched <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">Test Studio’s recorder</a> and recorded the following test steps:

![Recorded steps](/img/automated-tests/troubleshooting/handle-dynamic-attributes/2RecordedTest.png)

## Execute the Test and Explore the Results

Upon <a href="/automated-tests/test-execution/quick-execution" target="_blank">execution</a> of this sample test, we expect it to pass successfully. However, it fails to locate the element for step 2, which should click the button on the page. The failure listed in the <a href="/automated-tests/test-results/step-failure-details" target="_blank">Step Failure Details</a> is 'Element Not Found'.

Following the <a href="/automated-tests/troubleshooting/element-not-found" target="_blank">troubleshooting steps on handling an 'Element Not Found' error</a>, you find out that the button has a dynamic value for its __id__ attribute, which is different each time the page is reloaded.

If executed, this test fails, and editing the Element in Live reveals that the button has a dynamic id (it changes each time when the page is reloaded).

![Recorded steps](/img/automated-tests/troubleshooting/handle-dynamic-attributes/3EditElement.png)

Test Studio uses <a href="/features/project-settings/find-logic" target="_blank">an element identification scheme to auto-generate find expressions</a> for the recorded elements. The default scheme lists the __id__ attribute as a primary filter to be used in a find expression.

For the described scenario, using the __id__ attribute, though, is not reliable and there are few options to find a permanent solution for the failure.

> __Note__
><br>
><br>
> If the majority of elements in the application under test are using dynamic ids, you can change the order in which attributes are used when generating a find expression. The <a href="/features/project-settings/find-logic" target="_blank">Find Logic</a> tab in the _Project Settings_ allows you to reorder the attributes and also add custom tags, which correspond to the specifics of the tested page.

## How to Overcome the Trouble with Dynamic Elements?

When the specific page structure allows you to change the order of attributes used for generating the automatic find expressions, you can rely on the recorded elements and continue working on the test project with the modified settings.

But what if you need to handle only a single element on the page, which cannot be located properly? Test Studio provides few possible options:

* [Edit element’s find expression](#edit-elements-find-expression)
* [Locate element by image](#locate-element-by-image)
* [Use chained find expression](#locate-element-by-image)

### Edit Element’s Find Expression

Modifying the element’s find expression is usually the most straightforward, fastest, and robust approach to overcome the issue with not found elements.

If we get back to the example above, you can see that the __TextContent__ attribute of the _button_ element is unique for the element and is not changing. So if __TextContent__ is <a href="/automated-tests/elements/find-element#options-in-element-pane-with-active-recording-session" target="_blank">used in the find expression</a> instead of _id_, the test execution will not fail to locate and click the button.

![Change Find expression](/img/automated-tests/troubleshooting/handle-dynamic-attributes/4NewFindExpression.png)

### Locate Element by Image

Test Studio’s approach to record elements is quite enhanced and <a href="/automated-tests/elements/elements-find-expression#elements-image" target="_blank">it records an image</a> along with the automatically generated find expression. The <a href="/automated-tests/elements/find-element-by-image" target="_blank">recorded image for an element and its specific settings</a> can be found when an element is opened in _Edit_ mode.

![Search by image](/img/automated-tests/troubleshooting/handle-dynamic-attributes/5ImageSearch.png)

The image is, by default, used as __backup search criteria__ if the element find logic fails. In such case, the test will be marked as passed, and the only evidence that the element was found by using its image, is <a href="/automated-tests/test-results/analyze-quick-run-results#successful-test-run-with-warnings" target="_blank">a warning in the execution log</a>.

> __Note__
><br>
><br>
> If the application under test uses dynamic attributes and there is no set of attributes, which can be used to uniquely identify the elements, you can <a href="/features/project-settings/find-logic" target="_blank">adjust the primary approach to locate elements for a project to be __Search by image__</a>.

### Use Chained Find Expression

Adjusting <a href="/automated-tests/elements/using-chained-find-expressions" target="_blank">chained find expressions</a> is an advanced technique, but it comes quite handy to uniquely identify elements in more complex applications. The general idea is to use a parent element, which can be easily identified, and search for the actual element you are looking for within the unique parent element.

Using the sample test scenario from the beginning of this article and taking a closer look at the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a> of the page, reveals a possible parent _div_ element, which can be uniquely identified by its _id_ (it also seems to be static).

![Parent Element in Dom Explorer](/img/automated-tests/troubleshooting/handle-dynamic-attributes/6ParentElement.png)

Under that _div_ element, there is only one _button_, and it can be uniquely located by its _TagName_ attribute. The find expression which will represent locating these two elements in chain looks like this:

![Chained find expression](/img/automated-tests/troubleshooting/handle-dynamic-attributes/7ChainedFindExpression.png)
 
> __Note__
><br>
><br>
> You can use any of the attributes to locate the parent element, and then the child under that parent element.

You can find a real user scenario on how to automate SPA (Single Page Applications) with Test Studio and its ability to build chained find expressions in <a href="https://www.telerik.com/blogs/purposeful-find-logic-enhancement-chained-find-expressions" target="_blank">this blog post</a>.