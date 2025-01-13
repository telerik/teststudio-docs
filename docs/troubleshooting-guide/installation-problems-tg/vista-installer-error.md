---
title: Vista Installer Error
page_title: Vista Installer Problem
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: false

---
# Vista Installer Problem

## PROBLEM

 When I try to install on Windows Vista it says: 

"*There is a problem with this Windows Installer package. A program required for this install to complete could not be run. Contact your support personnel or package vendor.*"


## SOLUTION

This is caused by trying to install as a regular user (default install mode) instead of as the administrator. Follow this procedure: 


1.&nbsp; Copy the .msi to a folder on your machine.

2.&nbsp; Start a command prompt with Admin privileges. [On the start menu, highlight the command prompt and right-click-> Run as admin]

3.&nbsp; Navigate to the .msi and launch it from there.

