---
title: Remote Load Test Execution
page_title: Remote Load Test Execution
description: "How Test Studio executes load test in remote machines environment. Use multiple machines for laod testing with Test Studio"
position: 1
---
# Remote Load Test Execution

One of the main goals of load testing is to run a great amount of web requests against a web server. Usually this cannot be achieved efficiently if using a single machine. To perform a real load on an application server it is necessary to use as many physical machines as possible. For such load testing scenario the following conditions need to be present:

## Prerequisites

 - A <a href="/general-information/test-studio-run-time" target="_blank">Run-Time</a> version installed on each execution machine.
 - Scheduling and storage server <a href="/getting-started/installation/add-services" target="_blank">installed</a> and <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">configured</a> on one of the machines in the setup.
 - All execution clients have to be <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">connected</a> to the scheduling server machine.
 - Sufficient amount of <a href="/features/testing-types/load-testing/managing-vu" target="_blank">users</a> allocated on the machine which acts as a scheduling server.

## Running the tests

1. Create a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> that  contains a load test to be executed.
2. Assign sufficient amount of <a href="/features/testing-types/load-testing/managing-vu" target="_blank">virtual users</a> to the machine which acts as a scheduling server. The virtual users amount should correspond to the execution machines which will be used and their CPU units amount. Approximately 8 users per CPU unit seems to be sufficient to have a realistic load testing results. If a lot more users are allocated the web requests, that can not be executed due to overload of the CPU of execution machine, will be sent to a queue.
3. <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">Schedule the test list</a> to be executed using the option 'Distribute tests among these machines'.
