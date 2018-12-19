---
title: Dialog Handling Fails
page_title: Dialog Handling Fails
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Dialog Handling Fails

## PROBLEM

In multiple browsers, dialog handling fails to enter dialog field text or click dialog buttons accurately.

## SOLUTION

Conflicts with automatic form completion software can cause this behavior in dialog handler execution. Specifically, <a href="http://www.roboform.com/" target="_blank">RoboForm</a> can conflict with Test Studio dialog handling in this manner. Uninstalling RoboForm can resolve this behavior.