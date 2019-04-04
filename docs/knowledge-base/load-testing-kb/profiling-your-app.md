---
title: Profiling Your App
page_title: Profiling Your App
description: Profiling Your App in Test Studio load test. Identifying performance metrics to gather and analyze. Role-specific Metrics - Application Server (performance counters to measure the resource usage of different components of the application server). Database Server (performance counters to measure the behavior and resource usage of your SQL database server). Execution Server (performance counters to determine if the machine executing the load test is a bottleneck).
position: 1
---
#Profiling Your App#

When you load test your application with Test Studio, the Load Testing tool automatically <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">calculates metrics</a> about the HTTP traffic it receives from your application server. But some of the most important data about your application's performance comes from directly observing performance counters on the application and database servers. Test Studio's Execution Server and Standalone versions provide a Profiler for the machine where they are installed. By adding a machine to a Test Studio Load Test under <a href="/features/testing-types/load-testing/monitor-perf-metrics" target="_blank">Monitor Performance</a>, you can gather robust information about the performance of any machine in your application topology.

##Identifying Metrics##

You may select which performance metrics to gather and analyze in a number of ways.

###Requirements###

Project stakeholders may provide you with requirements that directly correspond to specific performance metrics. For example, the application may have a requirement that it must support over 1000 simultaneous users. This corresponds to a stress test in which the total number of virtual users surpasses 1000.

###Derived metrics###

You can also derive specific metrics from your application requirements. For example, the application may have a requirement that users begin to see responses to their actions within one second on average. From this requirement, you can derive a <a href="/features/testing-types/load-testing/running-tests" target="_blank">goal</a>: "Average Time to First Byte is Less Than 1000 ms."

#Role-specific Metrics#

Depending on the specific role of a machine in your application topology, you can select a different set of performance counters to monitor during your load test. Because every application has its own distinct architecture, each load test may have its own set of appropriate performance counters. Talk to your developers about which performance counters are most relevant for your application. Consider these as a starting point.

###Application Server###

Consider monitoring these performance counters to measure the resource usage of different components of the application server.

* Memory\ Available bytes

* Memory\ Cache Faults/sec

* Processor\ % Processor Time

* Physical Disk\ Avg. Disk Read Queue Length

* Network Interface\ TCP Connection Failures

* Server\  Bytes Transmitted/sec

For .NET applications, consider monitoring these .NET performance counters:

* .NET CLR LocksAndThreads\ Global\ Contention Rate /sec

* .NET CLR LocksAndThreads\ Global\ Queue Length / sec

* .NET CLR Memory\ # Bytes in all Heaps

* .NET CLR Memory\ % Time in GC

###Database Server###

Consider monitoring these performance counters to measure the behavior and resource usage of your SQL database server.

* Buffer Manager\ Buffer Cache Hit Ratio

* Buffer Manager\ Page life expectancy

* SQL Statistics\ Batch Requests/sec

* SQL Statistics\ SQL Compilations/sec

* Locks\ Lock Waits/sec: _Total

* General Statistics\ Processes Block

* Databases\ Active Transactions

###Execution Server###

Consider monitoring these performance counters to determine if your <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">Execution Server</a> is a bottleneck in your load test.

* Memory\ Available bytes

* Processor\ % Processor Time

* Network Interface\ Bytes Received/sec

* .NET CLR LocksAndThreads\ Telerik.TestStudio.RemoteExecutor \ ContentionRate /sec

##See Also##

* <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/aa373083(v=vs.85).aspx" target="_blank">Performance Counters at MSDN</a>

* <a href="http://msdn.microsoft.com/en-us/library/w8f5kw2e.aspx" target="_blank">.NET Performance Counters at MSDN</a>