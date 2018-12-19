---
title: Find Element Timeout
page_title: Find Element Timeout
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Find Element Timeout


## Problem

When navigating to a Silverlight application, the navigate step succeeds, but while the Silverlight app is loading, the second step fails. The error log displays an 'Unable to locate element' error for the target element.

## SOLUTION

This issue is caused by the Silverlight plugin not loading before the second step navigates. The solution is to enable the 'Use StepWaitOnElementsTimeout' test step property for the failing step after the navigate, and increase the 'WaitOnElementsTimeout' test step property to allow the plugin to load (for example, to 30000 ms). 

