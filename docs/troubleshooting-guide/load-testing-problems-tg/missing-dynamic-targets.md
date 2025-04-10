---
title: Missing Dynamic Targets
page_title: Missing Dynamic Targets
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Missing Dynamic Targets

## PROBLEM

Test Studio Load Testing does not capture <a href="/features/testing-types/load-testing/dynamic-targets" target="_blank">Dynamic Targets</a> from your application.

## SOLUTION

In Test Studio versions 2013 R1 and earlier, Load Tests will not detect dynamic targets using <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec3.html#sec3.6.1" target="_blank">chunked transfer encoding</a>. Upgrading to 2013 R2 or later should resolve this behavior.

