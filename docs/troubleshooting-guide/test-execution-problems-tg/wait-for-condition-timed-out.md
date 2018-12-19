---
title: Wait for Condition Timed Out
page_title: Wait for Condition Timed Out
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Wait for Condition Timed Out

## PROBLEM

You may encounter the *Wait for condition* has timed out error after your test performs a click action.

<pre>
Failure Information:
 ~~~~~~~~~~~~~~~
Wait for condition has timed out
InnerException:
System.TimeoutException: Wait for condition has timed out
at ArtOfTest.WebAii.Core.Browser.WaitUntilReady()
</pre>

This indicates the test timed out waiting for the browser to return to a "ready" state after the click command was sent to it.

## SOLUTION

This can often be overcome by setting the applicable step's **SimulateRealClick** property to True. Find it under the Behavior heading in the Properties pane.

![SimulaterRealClick][1]

When set to **True**, Test Studio will not wait for the browser to return to a "ready" state. Also, it will not automatically refresh its local copy of the DOM. Instead it sends the click command to the browser (as a live user would) and immediately moves on to the next test step.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/wait-for-condition-timed-out/fig1.png