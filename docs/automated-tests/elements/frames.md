---
title: Frames in the Elements Explorer
page_title: Frames in the Elements Explorer
description: "Test Studio Frames support. How are frames recognized in Test Studio test execution. How to handle dynamic frames? A frame is dynamic and Test Studio test run fails by each execution. Test Studio cannot find a frame. Test fails with 'Unable to find the target host' message. Frame Not Found Error message"
position: 6
---
# Frames in the Elements Explorer

Test Studio uses a built-in mechanism to detect HTML frames in the DOM tree of the tested application. The frames are represented as separate nodes in the Elements Explorer hierarchy.

This article describes how frames are identified during test run-time and how you can modify their properties.

## Frame Node

When there is an action against a frame, the elements get recorded under an additional node in the Elements Explorer. This node represents the frame and, in Test Studio, we call it a __Frame Node__.

![Frame nodes](/img/features/elements-explorer/frames/fig0.png)

## Properties and FrameInfo

The Frame node has its own properties, which can be accessed through the <a href="/automated-tests/elements/overview#elements-explorer-context-menu" target="_blank">context menu in the Elements Explorer</a> and explored in the Properties pane.

![Frame node properties](/img/features/elements-explorer/frames/fig1.png)

The __*FrameInfo*__ property contains the frame specific info, which is used from Test Studio to locate the frame on the web page when a test is executed.

![FrameInfo properties](/img/features/elements-explorer/frames/fig2.png)

> __Note__
><br>
><br>
> If a recorded element is listed under a frame node, during test run-time __Test Studio first locates the frame on the page__, next the test searches the element and then is the step action executed.

## Frames Identification Priority

The __Id__, __Name__ and __BaseUrl__ properties of the frame element in Test Studio should match a frame on the page with the same properties. If this logic cannot find any frame on the page, the __Index__ will be used as a back-up search logic.

* __Id__ and __Name__ accept partial string match, if the used value starts with tilde character (~);
* __BaseUrl__ is the frame's effective source value and takes into consideration the __UseQuery__ flag; This property also accepts partial match, if the tilde character (~) is used, and can be configured for <a href="/knowledge-base/test-execution-kb/base-url#using-the-baseurl-with-frames" target="_blank">BaseURL set on project level</a>;
* __Index__ - Test Studio sees all frames on the page in a flat list in the order they were loaded and this is how the index for each frame is generated. It is zero based and is recommended to use it as last resort;

## How to Handle Dynamic Frames

___What are dynamic frames?___ These are frames, which have different __FrameInfo__ properties each time when the page under test loads the frame. Any of the __Id__, __Name__ or __BaseUrl__, including a combination of these, can be dynamic, depending on how the application is built.

___What happens in the next test execution, if a frame is not located on the page?___ This usually happens when any of the frame properties are dynamic and don't match next time when the page and frame are loaded. There is an error message listed in the <a href="/automated-tests/test-results/analyze-quick-run-results#generate-the-quick-execution-log" target="_blank">test execution log</a>:

``` XML
Unable to find the target host (Browser/SilverlightApp) to locate an element. Failure: Waiting for frame '[Frame:id=<>,name=<>,src=<>,UseQuery:False]' timed out. Error: Wait for condition has timed out
InnerException:
System.Exception: Unable to find the target host (Browser/SilverlightApp) to locate an element. Failure: Waiting for frame '[Frame:id=<>,name=<>,src=<>,UseQuery:False]' timed out. Error: Wait for condition has timed out
   at ArtOfTest.WebAii.Design.Execution.ExecutionUtils.WaitForAllElements(IAutomationHost host, AutomationDescriptor descriptor, Int32 timeout, Int32 imageSearchTimeout, Int32 imageSearchDelay, Boolean searchByImageFirst)
   at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.ExecuteStep(Int32 order)

```

___How can the dynamic frame be identified for each test run?___ Each of the properties __Id__, __Name__ and __BaseUrl__ accepts the tilde (~) character to indicate partial match for the string. __BaseUrl__ property for the frame accepts also caret character (^), if <a href="/knowledge-base/test-execution-kb/base-url#using-the-baseurl-with-frames" target="_blank">BaseURL is set on project level</a>. If there is a dynamic query in the URL, ensure __UseQuery__ property is set to false.

![Dynamic frame](/img/features/elements-explorer/frames/fig3.png)

## What Happens If I Modify the Frame Properties

When adjusting the __FrameInfo__ properties to match the dynamic properties of frames in the tested page, all frame nodes which uses matching properties will be <a href="/automated-tests/elements/merge-page-nodes" target="_blank">merged into a single node in the Elements Explorer</a>.

If you record new steps in the test/project against a frame on the tested page, which properties matches these of an existing frame node (__including partial match if set__), the new elements will be listed under that existing frame node in the Elements Explorer.

> __Note__
><br>
><br>
> The __BaseURL set on project level__ is not considered during recording session. Frame nodes, which are using the caret character (^) to substitute the __BaseURL__ FrameInfo property will __not match newly added elements and frames__.
><br>
> To __avoid constant adjustment of frame nodes__, it is recommended to apply the __BaseURL__ settings for the frames at a final stage for the test project state.
