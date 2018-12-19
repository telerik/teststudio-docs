---
title: Java Flash ActiveX
page_title: Java Flash ActiveX
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Recording Java Plugins, Flash Objects, ActiveX Controls, and Chrome Frames


## PROBLEM

I am recording actions against a Java plugin, Flash object, ActiveX control, or Google Chrome Frame. No corresponding steps are recorded in Test Studio, however.

## SOLUTION

Test Studio sees Java plugins, Flash objects, ActiveX controls, and Google Chrome Frames as a single block \<object> or \<applet> element and cannot distinguish the individual components within it. It's basically a black box and the best alternative is to <a href="/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click" target="_blank">Invoke Blind Mouse Clicks</a> and <a href="/troubleshooting-guide/test-execution-problems-tg/invoke-blind-keyboard-typing" target="_blank">Blind Keyboard Typing</a> on it.

