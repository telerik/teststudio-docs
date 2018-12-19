---
title: No Results Data
page_title: No Results Data
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# No Results Data

## PROBLEM
Running a load test does not generate results data.

## SOLUTION
This behavior may occur if the sampling period for the load test is equal to or greater than the duration of the load test. To resolve this issue:

1.&nbsp; In the **Run** screen of the load test, decrease the sampling period.

![Sampling Rate][1]

2.&nbsp; Run the load test again.

[1]: /img/troubleshooting-guide/load-testing-problems-tg/no-results-data/fig1.png