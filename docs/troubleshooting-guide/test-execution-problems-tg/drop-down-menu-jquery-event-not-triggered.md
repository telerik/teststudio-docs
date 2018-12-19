---
title: Drop-down menu jQuery Event Not Triggered
page_title: Drop-down menu jQuery Event Not Triggered
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Drop-down menu jQuery Event Not Triggered

## PROBLEM

When executing a test against an HTML drop-down menu, Test Studio does not trigger the jQuery event associated with the drop-down.

## SOLUTION

A test step targeting an HTML drop-down with a jQuery event automatically triggers the event. There is no code required. A step recorded against this scenario has a <a href="/features/test-maintenance/test-step-properties" target="_blank">test step property</a> **TriggerjQueryEvent**, which is automatically set to 'True'. Test steps with this property enabled will handle the jQuery event associated with the drop-down.

![Trigger jQuery][1]

[1]: /img/troubleshooting-guide/test-execution-problems-tg/drop-down-menu-jquery/fig1.png


