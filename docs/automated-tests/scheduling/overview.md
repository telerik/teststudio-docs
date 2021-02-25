---
title: Scheduling Setup in Test Studio
page_title: Scheduling Test Runs (Standalone only)
description: "Test Studio Scheduling setup, Test Studio Scheduling configuration. Schedule Test List Runs, Run test lists remotely. How to configure the Test Studio Scheduling setup. What to use the Test Studio scheduling for"
position: 1
---
# Scheduling Configuration in Test Studio

The Test Studio Scheduling setup allows you to configure a set of machines, connected together to execute the automated tests unattended. The results generated from the scheduled test runs are stored in a way to allow anyone in the team to review these.

From your local instance of Test Studio test lists can be scheduled on any configured machine in the network, including virtual machines. The test list runs can be fully configured - when to be executed, on which machines, in case there are multiple available, whether to generate an automatic email report, etc. If you have to run a number of tests, you can spread the workload between different machines in order to reduce the total execution time. All the results will be stored in one centralized location for you to examine later.

## Which Are the Scheduling Setup Components?

Test Studio Scheduling setup consists of few services on top of the default product installation, which needs to be configured properly to allow the communication between them.

The Test Studio services, which needs to be added are as follows:

- __Scheduling Service__
- __Storage Service__
- __Executive Dashboard Service__

> __Tip__
> <br>
> <br>
> The Test Studio Services are __not included in the default Test Studio installation__, but __can be added in the installation__ later at any time. The __Test Studio Run-time installation includes the Services in its default state__.

## How Many Machines Do I Need?

The Scheduling configuration can be enabled on a single machine, as well as it supports multiple execution machines.

> __Note__
> <br>
> <br>
> Each machine, which will act as an __Execution server, requires minimum Test Studio Run-time installation__.

The Scheduling configuration can be __completely enabled on a single machine__ with the Test Studio Ultimate or Test Studio Web&Desktop installation (<a href="/prerequisites/installation/add-services" target="_blank">modified to include the services</a>).

If there are __multiple machines dedicated for test execution__, you need:
- at least __one machine with the Test Studio Ultimate or Test Studio Web&Desktop__ installation (can use the default installation) - it will be used to create  the tests for the automated testing project; 
- __one machine, which hosts the Test Studio services__ - this can be any of the machines in the setup, so it can use either full product installation, or Run-time edition instance;
- and at least __one machine to execute test lists - this one needs minimum the Run-time installation__.

![Scheduling Scheme][1]

## How to Configure the Scheduling Setup?

There are few steps to follow in order to setup the Scheduling configuration:

1. __Choose a machine, which will host the Test Studio Services__

    In Test Studio we call this machine the __Scheduling server__ - it can be any of the available machines as long as it is accessible for all other machines. It can be considered the __centralized component__, which communicates with all other parts of the configuration.
2. __Add/Install the Test Studio Services__

    Depending on which machine in the setup you have decided to host the Services - either <a href="/prerequisites/installation/add-services" target="_blank">modify the installation</a> of the Standalone Test Studio, or <a href="/prerequisites/installation/run-time-install" target="_blank">install the default Run-time product</a>.
3. __Configure the Services__

    The Scheduling config wizard allows you to setup each of the Services.
4. __Connect the Execution Machines to the Scheduler__

    The Execution machines are also called __Execution Servers__ in Test Studio - these are all machines, which are dedicated to execute the tests. The minimum installation for these is the Run-time edition of Test Studio - you can even <a href="/prerequisites/installation/run-time-install#customize-the-test-studio-run-time-installation" target="_blank">disable the Test Studio services from the installed components</a>, if there is already a machine, which hosts these.
5. __Configure Any Project for Remote Execution__

    Once the machines and components are set up, you need to <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connect a project to the Scheduler</a> - that way the __scheduled test list runs will go through the configured Services__.

Once these prerequisites are complete - even if each of these is on one machine, the scheduled test list executions will use the Test Studio Services with all their benefits - recurring runs, test distribution on selected machines, automatic email notification, results in the Executive Dashboard, etc.

[10]: /img/features/scheduling-test-runs/overview/fig1.png
[1]: /img/automated-tests/scheduling/overview/scheduling-iconography-bright.png