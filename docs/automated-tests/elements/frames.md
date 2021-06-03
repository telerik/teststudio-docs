---
title: Frames in the Elements Explorer
page_title: Frames in the Elements Explorer
description: "Test Studio Frames support. How are frames recognized in Test Studio test execution. How to handle dynamic frames? A frame is dynamic and Test Studio test run fails by each execution. Test Studio cannot find a frame. Test fails with 'Unable to find the target host' message"
position: 6
---
# Frames in the Elements Explorer

Test Studio uses a built-in mechanism to detect HTML frames in the DOM tree of the tested application when executing the recorded tests. The frames are represented as separate items in the Elements Explorer hierarchy.

This article describes how frames are identified during test run-time and how you can modify their properties.

## Frame Node

When there is an action against a frame, the elements get recorded under an additional node in the Elements Explorer. This node represents the frame and, in Test Studio, we call it a __Frame Node__.

![Element explorer][1]

## Properties and FrameInfo

The Frame node has its own properties, which can be accessed through the context menu in the Elements Explorer and explored in the Properties pane. The *FrameInfo* property contains the frame specific info, which is used from Test Studio to locate the frame on the web page when a test is executed.

![Frame properties][2]

> __Note__
><br>
><br>
> When a recorded element is listed under a frame node, then the __frame must be found first__ before Test Studio test can interact with that element during the test run.

## Frames Identification Priority

The __Id__, __Name__ and __Src__ properties of the frame element in Test Studio should match a frame on the page with the same properties. If this logic cannot find a frame on the page, the __Index__ will be used as a back-up search logic.

* __Index__ - Test Studio sees all Frames on the page in a flat list. Used as last resort; zero based.
Src - the frame's effective Src value, taking into consideration the UseQuery flag.

## Frame Not Found

When a frame cannot be found, you'll receive an error message like this:

``` XML
Unable to find the target host (Browser/SilverlightApp) to locate an element. Failure: Waiting for frame '[Frame:id=<>,name=<>,src=<>,UseQuery:False]' timed out. Error: Wait for condition has timed out
InnerException:
System.Exception: Unable to find the target host (Browser/SilverlightApp) to locate an element. Failure: Waiting for frame '[Frame:id=<>,name=<>,src=<>,UseQuery:False]' timed out. Error: Wait for condition has timed out
   at ArtOfTest.WebAii.Design.Execution.ExecutionUtils.WaitForAllElements(IAutomationHost host, AutomationDescriptor descriptor, Int32 timeout, Int32 imageSearchTimeout, Int32 imageSearchDelay, Boolean searchByImageFirst)
   at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.ExecuteStep(Int32 order)

```

This is often due to a dynamic frame Id or Name. This is remedied by using the tilde (~) character to indicate a partial match. This can be used in the BaseURL, Id, and Name fields. If the Src string contains a dynamic query, set UseQuery to False.

![Dynamic frame][3]

[1]: /img/features/elements-explorer/frames/fig1.png
[2]: /img/features/elements-explorer/frames/fig2.png
[3]: /img/features/elements-explorer/frames/fig3.png
