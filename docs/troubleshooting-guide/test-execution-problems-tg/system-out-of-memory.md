---
title: System Out of Memory
page_title: System.OutOfMemoryException
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# System.OutOfMemoryException

## PROBLEM

My data driven test has hundreds or thousands of iterations. It fails during execution with one the following errors:

- *EXCEPTION! (see below)<br>
  Outer Exception Type: System.OutOfMemoryException<br>
  Message: Exception of type 'System.OutOfMemoryException' was thrown.*

- *Error attempting to execute a Test As Step. Details:<br>
  System.OutOfMemoryException: Out of memory.*


## SOLUTION

A test with that many iterations is very likely to encounter memory issues deep into execution. To combat this, use the **ReuseAppWindow** feature available in the <a href="/features/test-maintenance/test-properties-standalone" target="_blank">Test Properties</a>. This defines the number of iterations to reuse the browser window for a single test.

![ReuseApp][1]

By default, zero keeps the same application open during the entire data driven test. Increasing that number can help to improve memory and performance. For example, a value of 50 causes the browser/app to close and reopen after every 50 iterations.

## PROBLEM

When executing a test in Internet Explorer 9 on a Windows 7 32-bit or Windows XP machine, ArtOfTest.Runner exits unexpectedly, displaying this error:

- *EXCEPTION! (see below)<br>
  Outer Exception Type: System.OutOfMemoryException<br>
  Message: Exception of type 'System.OutOfMemoryException' was thrown.*

However, there is sufficient available system memory. 

## SOLUTION

This error is caused by the Microsoft UI Automation framework, which Test Studio uses to monitor dialogs. To avoid it, enable the **DisableDialogMonitoring** <a href="/features/test-maintenance/test-properties-standalone" target="_blank">Test Property</a> or <a href="/getting-started/test-execution/test-list-settings" target="_blank">Test List Setting</a>. Note: this will prevent your test from handling dialogs.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/system-out-of-memory/fig1.png
