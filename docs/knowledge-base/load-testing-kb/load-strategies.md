---
title: Load Strategies
page_title: Load Strategies
description: Choose which load strategy will suit the current requirements and adjust the Test Strudio load test accordingly. Stress Testing. Baseline Tests and High Load Tests. Soak Testing. Scalability Testing. Geographic Diversity Testing. 
position: 1
---
## Types of Load Tests

There are many types of load tests, each designed to answer specific questions. Here are four common types of load test, and how to start building them in Test Studio.

## Stress Testing

A typical stress test begins with a small amount of load and slowly increase this amount throughout the test. This test type answers these questions:

* How many users can my application support without failing?

* How many users can my application support without slowing down?

* What are the performance bottlenecks that limit the load my application can support?

In Test Studio, create a stress test by increasing the <a href="/features/testing-types/load-testing/test-settings" target="_blank">number of Virtual Users</a> (VUs) in your Load Test throughout the test.

Users Over Time for a stress test is a diagonal line from low to high:

![Virtual users][1]

If your Test Studio Load Test has enough VUs, the application under test will eventually begin to slow down and fail. Adding VUs slowly over time increases the precision of your results: you can determine how many VUs were hitting the application when it slowed or failed. 

Keep in mind that this type of test will eventually disable the target application, so plan accordingly. If you target a production server, consider planning the test for off-peak hours.

Once the test is completed, you can identify the time in the <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">results</a> that the application performance degrades or fails; then, you can identify <a href="/features/testing-types/load-testing/monitor-perf-metrics" target="_blank">performance counters</a> on the application or database server that explain why.

![Performance counters][2]

### Baseline Tests and High Load Tests

Two related load test types are **baseline tests** and **high load** tests. Unlike a stress test, these tests use a continuous number of VUs. A baseline test uses a number of VUs equal to the number of users the application is required to support; a high load test uses a number of VUs greater than the requirements. These tests can answer the questions, "Does my application support the required number of users?" and "Does my application support the target number of users?" You can also answer these questions by stress testing.

## Soak Testing

Soak tests (also known as **endurance tests**) apply a constant load to the target application for an extended period of time. This test type answers these questions:

* Does the performance of my application degrade over time?
* If so, why?


The duration of the test may be hours, days, or even weeks.

Users Over Time for a soak test is a flat line:

![Soak tests VU][3]

The amount of load is often the expected number of users, but you may also wish to soak test your application at multiple load levels. The purpose of the soak test is to identify problems in application performance that do not occur over shorter test durations, such as memory leaks. When analyzing the soak test results, make sure to analyze the performance counters on the application server to find patterns in resource usage.

## Scalability Testing

Scalability tests perform multiple load tests against different resource configurations. This test type tries to answer these questions:

* How does my application responds to an increase in the scale of application resources?

* What performance bottlenecks prevent my application from scaling properly? 

This could include a larger database, more application servers, or added resources on a VM or cloud instance. This type of test may also vary the server configuration of the application server.

Scalability tests correspond to different application and server configurations:

![Analyze results][4]

Keep in mind that some cloud services may not expose their performance counters to our Profiler, which is included in Test Studio Runtime and Standalone installations.

## Geographic Diversity Testing

Geographic diversity tests generate load from different locations. This test type tries to answer these questions:

* How will my application perform for users in different locations?

* Will different server locations improve this performance?

You can use Test Studio Load Testing to perform geographic diversity testing by installing and selecting <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution Servers</a> in different locations. These locations can simulate the locations of different users or user populations. You can compare the results from load tests run on a machine in one location with those run in another. Keep in mind that Test Studio Test Lists will be distributed automatically to different Execution Machines, so select one Execution Machine for each Test List in this type of test. Once you have performed this type of test, you may want to repeat the test with a different application server location to see if this improves results.

## See Also

* <a href="/knowledge-base/load-testing-kb/selecting-traffic" target="_blank">Selecting Load Traffic</a>

* <a href="/features/testing-types/load-testing/designing-tests" target="_blank">Designing Load Tests</a>

[1]: /img/knowledge-base/load-testing-kb/load-strategies/fig1.png
[2]: /img/knowledge-base/load-testing-kb/load-strategies/fig2.png
[3]: /img/knowledge-base/load-testing-kb/load-strategies/fig3.png
[4]: /img/knowledge-base/load-testing-kb/load-strategies/fig4.png



