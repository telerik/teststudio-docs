---
title: Unable to Load SC Plugin
page_title: Unable to Load Source Control Plugin
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---

# Unable to Load Source Control Plugin

## PROBLEM

You receive the following error when you attempt to integrate TFS in Test Studio Standalone version and you do not have Visual Studio installed:

![Plugin Error][1]

## SOLUTION

Install the appropriate version of <a href="http://www.microsoft.com/en-us/download/details.aspx?id=40776" target="_blank">Visual Studio Team Explorer</a>. This is the client SKU that allows you to access the TFS functionality.

> Even you have or you would install Visual Studio 2015 it does not include VS Team Explorer. In order to use our TFS integration, you need to install explicitly Team Explorer.

[1]: /img/troubleshooting-guide/installation-problems-tg/unable-to-load-sc-plugin/fig1.png


