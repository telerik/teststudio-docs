---
title: Frames
page_title: Frames | Test Studio Dev Documentation
description: Frames get automatically detected by Test Studio Dev. 
slug: features/recorder/frames
position: 2
---
# Frames

Frames are automatically detected by Test Studio. When you record an action or verification against an element within a frame, Test Studio adds an additional frame node to the Elements Explorer __add a link__.

![Element explorer](images/frame-node.png)

A frame has its own properties which determine how it is located. The frame must be found before acting upon the elements within it.

![Frame properties](images/frame-properties.png)

The identification priority for a frame is as follows:

* __Id__ - the preferred frame identification method.
* __Name__ - used only if Id is not set.
* __Src__ - the frame's effective Src value, taking into consideration the UseQuery flag.
* __Index__ - Test Studio sees all Frames on the page in a flat list. Used as last resort; zero based.

When a frame cannot be found, you'll receive an error message like this:

*Unable to find the target host (Browser/SilverlightApp) to locate an element. Failure: System.TimeoutException: Wait for condition has timed out
   at ArtOfTest.Common.WaitSync.CheckResult(WaitSync wait, String extraExceptionInfo)
   at ArtOfTest.Common.WaitSync.For\[T,V](Func`3 func, T target, V custom, Boolean invertCondition, Int32 timeout)
   at ArtOfTest.Common.WaitSync.For\[T,V](Func`3 func, T target, V custom, Int32 timeout)
   at ArtOfTest.WebAii.Core.Browser.WaitForFrame(FrameInfo frameInfo, Int32 timeout)
   at ArtOfTest.WebAii.Design.Execution.ExecutionUtils.GetFrameBrowserInstance(Browser topBrowser, FrameInfo frame, Int32 waitTimeout, String& stringError)*

This is often due to a dynamic frame Id or Name. This is remedied by using the tilde (~) character to indicate a partial match. This can be used in the BaseURL, Id, and Name fields. If the Src string contains a dynamic query, set UseQuery to False.

![Dynamic frame](images/dynamic-frame.png)
