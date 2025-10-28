---
title: No Results Data
page_title: No Results Data
description: "Troubleshoot the issue of missing results data in Test Studio load tests. Learn why results may not appear, how sampling period settings affect data collection, and steps to resolve common load testing problems."
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