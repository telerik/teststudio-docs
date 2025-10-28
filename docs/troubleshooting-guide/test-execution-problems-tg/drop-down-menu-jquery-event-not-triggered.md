---
title: Drop-down menu jQuery Event Not Triggered
page_title: Drop-down menu jQuery Event Not Triggered
description: "Find solutions for jQuery events not triggering on HTML drop-down menus during Test Studio test execution. Learn about the TriggerjQueryEvent property and how to ensure automated tests handle drop-down interactions correctly."
position: 1
---
# Drop-down menu jQuery Event Not Triggered

## PROBLEM

When executing a test against an HTML drop-down menu, Test Studio does not trigger the jQuery event associated with the drop-down.

## SOLUTION

A test step targeting an HTML drop-down with a jQuery event automatically triggers the event. There is no code required. A step recorded against this scenario has a <a href="/features/test-maintenance/test-step-properties" target="_blank">test step property</a> **TriggerjQueryEvent**, which is automatically set to 'True'. Test steps with this property enabled will handle the jQuery event associated with the drop-down.

![Trigger jQuery][1]

[1]: /img/troubleshooting-guide/test-execution-problems-tg/drop-down-menu-jquery/fig1.png


