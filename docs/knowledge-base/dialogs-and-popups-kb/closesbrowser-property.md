---
title: ClosesBrowser Property
page_title: ClosesBrowser Property
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Using the ClosesBrowser Property for Pop-ups#

Pop-ups can have a control (usually a button) which invokes an event that closes the pop-up. This can cause problems when performing UI Automation with Test Studio.

##Solution##

"Click"-type of steps have a property called "ClosesBrowser":

![ClosesBrowser property][1]

Depending on the implementation of the pop-up, Test Studio may or may not detect the cases where this property needs to be set to Ttrue. Symptoms related to this issue can be:

* Click steps timing out after the actual click occurred during execution.

* Click steps failing with a seemingly random exception message:

	*ExecuteCommand failed:
	BrowserCommand
	(Type:'Information', Info:'IsReady', Action:'NotSet', Tergaet:'null', Data:'', ClientID:'Client_034ab38c-2736-49b3-9b45-986d2990bc07', HasFrames:'False', frameInfo:'', TargetFrameIndex:'-1', InError:'False', Response:'')
	InnerException: System.IO.IOException: **Pipe is broken**.
		at System.IO.Pipes.PipeStream.WinIOError(Int32 errorCode)
		at System.IO.Pipes.PipeStream.WaitForpipeDrain()*

* If the click step is followed by a "Close pop-up window" step, this likely indicates the button invokes a Closing event. However, this problem can occur even if your test contains no "Connect to pop-up window" or "Close pop-up window" steps. This is because some pop-ups are implemented in a non-standard way. In these cases, set ClosesBrowser to True. Select the "Click" step, then change this setting from the Property menu on the right.

* Setting the Click step's **SimulateRealClick** property to True resolves the issue.
	
##See also##

* 	<a href="http://www.quirksmode.org/js/popup.html" target="_blank">This page</a> for an example of this kind of pop-up implementation.


[1]: /img/knowledge-base/dialogs-and-popups-kb/closesbrowser-property/fig1.png


