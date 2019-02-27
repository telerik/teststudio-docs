---
title: Unable to Show Data Tables In Excel Data Source
page_title: Unable to Show Data Data Tables in Excel Data Source
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Unable to Show Data Tables in Excel Data Source

## PROBLEM 1

If running a data driven test on remote machine you get your test failed and the following exception could be found in the log:

***The 'Microsoft.ACE.OLEDB.12.0' provider is not registered on the local machine***

> This could happen on machines with no Microsoft Office or Data Connectivity Component installed.

## PROBLEM 2

I am able to bind an excel file to be used for data driving a test but there are no sheets listed to select from:

![No sheets][1]

> This could be observed also if the Microsoft Office package is 64-bit version.

## SOLUTION

Download and install the <a href="https://www.microsoft.com/en-us/download/details.aspx?id=13255" target="_blank">Microsoft Access Database Engine 2010</a>. It will install the required drivers for communication between Test Studio and the Microsoft Office files for all of the above cases.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-show-data/fig1.png