---
title: Overview
page_title: Scheduling Test Runs Optionally Remotely (Standalone only)
description: "Test Studio Scheduling Test Runs, Optionally Remotely (Standalone only). Test Studio Scheduling allows you to select atest list to execute at a future time, set the date and time for the test run and return later to see the results. The Scheduling Service could be also used to schedule a test list to run on remote execution machines."
position: 1
---
# Scheduling Test Runs, Optionally Remotely (Standalone only)

Test Studio Scheduling allows you to select a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a> to execute at a future time, set the date and time for the test run and return later to see the results. The Scheduling Service could be also used to schedule a test list to run on remote machines.

From your local instance of Test Studio test lists could be scheduled on any machine in the network including virtual machines. If you have to run a number of tests, you can spread the workload between different machines in order to reduce the total execution time. All the results will be stored in one centralized location for you to examine later.

Below is a diagram of the Scheduling setup and how its components communicate between each other: 

![Scheduling Scheme][1]

## Differences between Local and Remote Scheduling Setup

Depending on the scheduling scenario setup will vary. There are two main scenarios:

- &nbsp; <a href="/features/scheduling-test-runs/local-scheduled-run" target="_blank">**Test Studio default installation**</a>, which allows you to create and execute tests, create and schedule test lists locally, all on one machine.

- &nbsp; <a href="/features/scheduling-test-runs/remote-run-all-in-one" target="_blank">**Remote execution installation**</a>, where the Test Studio Standalone installation, Scheduling and Storage Servers and Execution client could be **optionally** on more than one machine.

### Local setup

The local all-in-one setup allows you to <a href="/features/scheduling-test-runs/local-run-all-in-one" target="_blank">schedule the test lists</a> for a certain time in the future. The execution is on the same machine and complete standalone installation of Test Studio is sufficient to setup that configuration.

### Remote Setup

The remote configuration allows you to execute and/or schedule test lists on multiple machines <a href="/knowledge-base/test-execution-kb/multi-browsers#How-to-Run-Tests-in-Parallel" target="_blank">even simultaneously</a>.

The setup may vary from single to multiple execution machines. It only requires <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">**a Scheduling service**</a> and <a href="/features/scheduling-test-runs/create-storage-server" target="_blank">**a Storage service**</a> to be configured once on any of the machines and <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">all **Execution clients need to be connected to the configured Scheduling service**</a>.

The components of the remote Scheduling configuration may be all be installed on a single machine and thus, allow that single machine to simulate remote test list execution.

[1]: /img/features/scheduling-test-runs/overview/fig1.png