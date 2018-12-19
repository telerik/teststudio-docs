---
title: Test Runner Stays Open
page_title: Test Runner Stays Open
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Test Runner Stays Open

## PROBLEM

The Test Studio Test Runner process does not exit when you close Test Studio. 

## SOLUTION

This is by design: if there are still tests scheduled to run when you close Test Studio, or if the Test Runner was already running when you started Test Studio, the Test Runner will not exit when Test Studio closes. This is to ensure that Test Studio does not prevent scheduled test execution. 

