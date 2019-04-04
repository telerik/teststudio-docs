---
title: Virtual Users
page_title: Virtual Users
description: clarify some of the concepts behind Virtual Users in Test Studio Load Tests. Workload in Test Studio load test. How to adjust the workload of user profiles to cover the load test requirements.
position: 1
---
#Virtual Users#

This document attempts to clarify some of the concepts behind Virtual Users in Test Studio Load Tests.

## Workload ##

### Balancing Profiles ###

The Workload is the proportion that each User Profile will be used compared to all the User Profiles contained in the test. For example, if User Profile A is set to 80% while User Profile B is set to 20%, 80% of the load traffic will come from User Profile A, while 20% of the load traffic will come from User Profile B. If both user profiles are set to 20% (or any value that is the same), 50% of the load traffic will come from User Profile A and 50% of the load traffic will come from User Profile B.

### Parallel versus Distributed Execution ###

As of 2013 R1, Test Lists can run in <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Parallel Execution</a> mode. If load tests are executed in this mode, each Execution Server will utilize all VUs. If a Test List is run in Distributed mode instead, a Test Studio Load Test will evenly distribute the users across all of the available Execution Server. For example, if you specify 500 users and have 5 Execution Servers, each load agent will simulate 100 users.

To determine how Workload will affect the number of VUs assigned to a particular Execution Machine in Distributed Execution, divide all users equally between all agents, then apply workload ratios. For example, if the Load Test reaches 2000 concurrent users, and 4 Execution Server, then each Execution Server will be assigned 500 VU. If the Load Test has 2 user profiles with Workloads of 60% and 40%, then the first Profile will use 300 of the Execution Server's 500 VUs, and the second Profile will use 200 VUs.

Workloads determine the percentage of the Execution Server's VUs to apply to a User Profile:

![user profile][1]

### Available Users ###

Here you specify how many users to simulate while running the load test. Test Studio Load Tests will always increase or decrease concurrent users at a constant rate, resulting in a straight line between the number of starting and ending concurrent users.

Concurrent users increase at a constant rate:

![available users][2]

The minimum number of users for either entry is the total number of reporting test agents on the Execution Server multiplied by the total Workload divided by the smallest Workload and then rounded up to the next whole number. For example, if you have 1 Execution Machine with User Profile A set at 66% and User Profile B set at 33%, the calculation is this:

(1 * 100) / 33 = 3.03, which is then rounded up to 4. Thus the minimum number of virtual users for starting or ending is 4.

## See Also ##

* <a href="/features/testing-types/load-testing/managing-vu" target="_blank">Managing Virtual Users</a>

[1]: /img/knowledge-base/load-testing-kb/virtual-users/fig1.png
[2]: /img/knowledge-base/load-testing-kb/virtual-users/fig2.png
