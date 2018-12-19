---
title: Base test methods
page_title: Base test methods
description: Base test methods
publish: true
position: 5
slug: ms-basetest-methods
previous_url: /test-studio-mobile/getting-started-mb/code-features/coded-stepsd
---

#Base test methods

Every Native/Hybrid/Web mobile test inherits a base mobile test class that provides some additional functionality. For example, some code can be executed before the test is started or after the test is completed. In these cases you can override the `OnBeforeTestStarted` and `OnAfterTestCompleted` methods the base test class provides. The code bellow shows how to utilize this scenario and add sample test execution duration calculation to the test execution log.

```C#
protected override void OnAfterTestCompleted()
{
	Log.WriteLine("Test completed at: " + DateTime.Now.ToLongTimeString());
}
	
protected override void OnBeforeTestStarted()
{
	Log.WriteLine("Test started at: " + DateTime.Now.ToLongTimeString());
}
```
	
```VB
Protected Overrides Sub OnAfterTestCompleted()
	Log.WriteLine("Test completed at: " + DateTime.Now.ToLongTimeString())
End Sub

Protected Overrides Sub OnBeforeTestStarted()
	Log.WriteLine("Test started at: " + DateTime.Now.ToLongTimeString())
End Sub
```

Here is a completed view of the test code-behind file:

![Test Base Methods Code](/img/test-studio-mobile/getting-started-mb/coded-features/base-test-methods/code.png)

Executing the test provides a log file that contains the logged data:

![Test Base Methods Log](/img/test-studio-mobile/getting-started-mb/coded-features/base-test-methods/log.png)


See Also
--------

* [Coded Steps]({%slug ms-coded-steps%})
* [Code Item]({%slug ms-code-item%})
* [Code Behind File]({%slug ms-code-behind%})
* [Output Pane]({%slug ms-output-pane%})
* [Compile Project]({%slug ms-compile-project%})
* [Android API]({%slug ms-android-api%})
* [iOS API]({%slug ms-ios-api%})
* [Hybrid API]({%slug ms-hybrid-api%})
* [Web API]({%slug ms-web-api%})