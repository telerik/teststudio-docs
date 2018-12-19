---
title: Overview
page_title: Performance Testing
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/performance.aspx, /user-guide/performance
position: 1
---
# Performance Testing

Automated functional testing tools help you build automated tests for your critical end-user scenarios. Once automated, these scenarios can be run automatically to help discover any regressions. Functional correctness of your application is one measure of quality, another quite important one is performance testing. How responsive is my application? What are the bottlenecks in my application? How do I discover them and, most importantly, am I regressing or enhancing application performance with each build? These are questions Test Studio answers with the Performance testing functionality.


- **Performance Measuring & Benchmarking** - Take a functional scenario and measure each step's execution time. Measure not only the total time but also Client vs. Server time. Then create benchmarks to later compare against for regression detection or goal setting. 

- **Historical View & Comparison** - View the historical performance of your tests and compare two different snapshots to help identify where the regressions are happening.

- **In-Depth Analysis** - Analyze your results by comparing Client vs. Server time. Trace your code at the step level to pinpoint the exact line of code that is causing the biggest bottleneck. 

> If profiling a remote server, it needs at minimum the Test Studio Run-Time edition installed on it with the Profiler Service enabled. The versions of Test Studio run locally and remotely on the server must match. Also ensure the correct inbound and outbound <a href="/features/testing-types/performance-testing/open-port-on-server" target="_blank">port is open</a> on the remote server.

## Select a Valid Automated Web Test 

Which web tests make good candidates for Performance Testing?

- Specific user scenarios with little to no verification steps or timeouts.

- All variables are removed to prevent interference.

## Get Started

Once you designate a good candidate test, go to the **Performance** tab and get started:

1.&nbsp;  <a href="/features/testing-types/performance-testing/gather-perfomance-data" target="_blank">Gather Performance Data</a> - Configure settings and create the Performance Run.

2.&nbsp; <a href="/features/testing-types/performance-testing/history-view" target="_blank">History View</a> - Visualize metrics over time, achieve performance goals, and use the Benchmark feature to establish a performance baseline. 

3.&nbsp; <a href="/features/testing-types/performance-testing/overview-button" target="_blank">Overview</a> - View data related to the server, network, and client. 

4.&nbsp; <a href="/features/testing-types/performance-testing/details-view" target="_blank">Details View</a> - View an in-depth analysis of each test step, the entire test, or a custom interval.

5.&nbsp; <a href="/features/testing-types/performance-testing/compare-view" target="_blank">Compare View</a> - Put two Performance Runs side by side and identify potential regressions or bottlenecks using delta threshold.