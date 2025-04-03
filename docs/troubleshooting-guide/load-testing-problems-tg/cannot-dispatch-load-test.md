---
title: Cannot Dispatch Load Test
page_title: Cannot Dispatch Load Test
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Cannot Dispatch Load Test

## PROBLEM

When attempting to run a load test, the test list fails. The test list results for the load test contain this error: "Cannot Dispatch Load Test."

## SOLUTION

This error can occur when a firewall is blocking the port that the load test requires. The more load tests you run, the more open ports your Execution Server may require. To resolve this behavior:

- Ensure that any active firewall on the Execution Server(s) running the load test is not blocking the ports in the range 8030-8039.

- If this does not resolve the behavior, try unblocking a larger range of ports in the range above 8039 (for example, ports 8039-8059).

- If the behavior still occurs, try closing and re-opening the <a href="/features/scheduling-test-runs/overview" target="_blank">Test Studio Test Runner System Tray process</a>.


