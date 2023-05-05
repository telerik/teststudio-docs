---
title: Scheduling Setup in Test Studio
page_title: Scheduling Test Runs (Standalone only)
description: "Test Studio Scheduling setup, Test Studio Scheduling configuration. Schedule Test List Runs, Run test lists remotely. How to configure the Test Studio Scheduling setup. What to use the Test Studio scheduling for"
position: 1
---
# Scheduling Configuration in Test Studio

The Test Studio Scheduling setup allows you to configure a set of machines, connected together to execute the automated tests unattended. The results generated from the scheduled test runs are stored in a way to allow anyone in the team to review these.

Test Studio test lists can be executed from your local project on any machine in the network, including virtual machines, configured in the Test Studio Scheduling setup. The test list runs can be fully configured - when to be executed, on which machines, in case there are multiple available, whether to generate an automatic email report, etc. If you have to run a number of tests, you can spread the workload between different machines and reduce the total execution time. All the results will be stored in one centralized location for you to examine later.

You can find the following topics in this article:

- [Which Are the Scheduling Setup Components?](#which-are-the-scheduling-setup-components)
- [How Many Machines Do I Need?](#how-many-machines-do-i-need)
- [How to Configure the Scheduling Setup?](#how-to-configure-the-scheduling-setup)

## Which Are the Scheduling Setup Components?

Test Studio Scheduling setup consists of few services on top of the default product installation, which needs to be configured properly to allow the communication between them.

The Test Studio services, which needs to be added are as follows:

- [Scheduling Service](#scheduling-service)
- [Storage Service](#storage-service)
- [Executive Dashboard Service](#executive-dashboard-service)

> __Tip__
> <br>
> <br>
> The Test Studio Services are __not included in the default Test Studio installation__, but <a href="/prerequisites/installation/add-services" target="_blank">__can be added in the installation__ later</a> at any time.
> <br>
> <br>
> The __Test Studio Run-time installation includes the Services in its default state__.

### Scheduling Service

The Scheduling Service is the central component of the overall setup - it is in the middle of all operations and can be considered that it controls the process of running a test list on any remote machine. All execution clients, the Storage Service and the projects, from which tests are executed, are all connected to the same Scheduling service.

- __By default the Scheduling service uses port 8009__. It can be changed with any other free port for the specific environment in the _Scheduling config wizard_.
- Apart from the default set _localhost_, __the _Scheduling config wizard_ accepts IP address or machine name__ for pointing the computer, which hosts the Scheduling service.

<br>
<div><a style="float:right" href="#which-are-the-scheduling-setup-components">Back to top of section</a></div>
<br>

### Storage Service

The Storage Service, which keeps the project files and results, is the help tool for the Scheduling service. The Storage service maintains a database to store the files and the database provider, which Test Studio uses is <a href="https://www.mongodb.com" target="_blank">**MongoDb**</a>. The files from the Storage database gets deployed to the execution machines upon scheduled or remote test list run.

> __Note__
> <br>
> <br>
> The __installation of the third party component MongoDB is automatically triggered__ during the Storage service installation.
> <br>
> <br>
> If the Test Studio installation wizard detects an existing compatible MongoDB installation, this additional installation will be skipped.

- __By default the Storage service uses port 8492__. It can be changed with any other free port for the specific environment in the _Scheduling config wizard_.
- Apart from the default set _localhost_, __the _Scheduling config wizard_ accepts IP address or machine name__ for pointing the computer, which hosts the Storage service.
- The Storage Service uses the default connection string to connect to MongoDB. If you reconfigure MongoDB, you need to apply the changes in the _Scheduling config wizard_ as well.
- The Scheduling server contacts the Storage Service for every scheduled job or results review. The Storage Service communicates internally to the MongoDB database to provide the queried info.

<br>
<div><a style="float:right" href="#which-are-the-scheduling-setup-components">Back to top of section</a></div>
<br>

### Executive Dashboard Service

The Executive Dashboard is the tool, which provides access to all results generated from scheduled test list runs for all team members - including these, who do not have Test Studio installed. The Executive Dashboard service hosts a _localhost_ page on the machine, where the service is installed. The local web page visualizes the results stored in the storage database.

- __By default it uses port 8085__. It can be changed with any other free port for the specific environment in the _Scheduling config wizard_.
- The Executive Dashboard service communicates with the configured Storage service. So, if you reconfigure the Storage Service, you need to change the details for the Executive Dashboard Service as well.
- The _localhost_ page can be loaded from the _Scheduling config wizard_.

> __Important__
> <br>
> <br>
> Initial configuration or any follow-up changes in the __Test Studio Scheduling configuration must be applied from a Windows Administrator account__.

<br>
<div><a style="float:right" href="#which-are-the-scheduling-setup-components">Back to top of section</a></div>
<br>

## How Many Machines Do I Need?

The Scheduling configuration can be enabled on a [single machine](#single-machine-scheduling-configuration), as well as it supports [multiple execution machines](#multiple-machines--scheduling-configuration).

> __Note__
> <br>
> <br>
> Each machine, which will act as an __Execution server, requires minimum Test Studio Run-time installation__.

### Single Machine Scheduling Configuration

The Scheduling configuration can be __completely enabled on a single machine__ with the Test Studio Ultimate or Test Studio Web&Desktop installation (<a href="/prerequisites/installation/add-services" target="_blank">modified to include the services</a>).

### Multiple Machines  Scheduling Configuration

If there are __multiple machines dedicated for test execution__, you need:

- at least __one machine with the Test Studio Ultimate or Test Studio Web&Desktop__ installation (can use the default installation) - it will be used to create  the tests for the automated testing project;
- __one machine, which hosts the Test Studio services__ - this can be any of the machines in the setup, so it can use either full product installation, or Run-time edition instance;
- and at least __one machine to execute test lists - this one needs minimum the Run-time installation__.

![Scheduling Scheme][1]

> __Tip__
> <br>
> <br>
> Find out more about the __Test Studio Scheduling architecture__ in <a href="https://www.telerik.com/blogs/architecture-remote-execution-test-studio" target="_blank">this blog post</a>.

## How to Configure the Scheduling Setup?

There are few steps to follow in order to setup the Scheduling configuration:

1. __Choose a machine, which will host the Test Studio Services__

    In Test Studio we call this machine the __Scheduling server__ - it can be any of the available machines as long as it is accessible for all other machines. It can be considered the __centralized component__, which communicates with all other components of the configuration.
2. __Add/Install the Test Studio Services__

    Depending on which machine in the setup hosts the Services - either <a href="/prerequisites/installation/add-services" target="_blank">modify the installation</a> of the Standalone Test Studio, or <a href="/prerequisites/installation/run-time-install" target="_blank">install the default Run-time product</a>.
3. __Configure the Services__

    The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling config wizard</a> allows you to setup all Test Studio Services. The default ports used for the Scheduling communication are registered for non-admin users with the installation of the services. Re-applying the settings, or changing the ports requires Admin user permissions.
4. __Connect the Execution Machines to the Scheduler__

    The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server" target="_blank">Execution machines</a> are also called __Execution Servers__ in Test Studio - these are all machines, which are dedicated to execute the tests. The __minimum installation for these is the Run-time edition__ of Test Studio. If there is already a Scheduling server machine, you can <a href="/prerequisites/installation/run-time-install#customize-the-test-studio-run-time-installation" target="_blank">disable the Test Studio services from the installed components</a> on the Execution machines.
5. __Configure Any Project for Remote Execution__

    Once the machines and components are set up, you need to <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connect a project to the Scheduler</a> - that way the __scheduled test list runs will go through the configured Services__.

When these prerequisites are complete - including the case when all these components are hosted on the same machine, the __scheduled test list executions will use the Test Studio Services with all their benefits__ - <a href="/automated-tests/scheduling/schedule-execution#step-1" target="_blank">recurring runs</a>, <a href="/automated-tests/scheduling/schedule-execution#step-2" target="_blank">test distribution</a> on selected machines, <a href="/automated-tests/scheduling/schedule-execution#step-3" target="_blank">automatic email notification</a>, results in the <a href="/automated-tests/scheduling-results/dashboard/results" target="_blank">Executive Dashboard</a>, etc.

## See Also

* <a href="https://www.telerik.com/blogs/architecture-remote-execution-test-studio" target="_blank">The Architecture of Remote Execution With Test Studio</a>

[10]: /img/features/scheduling-test-runs/overview/fig1.png
[1]: /img/automated-tests/scheduling/overview/scheduling-setup-revamp.png