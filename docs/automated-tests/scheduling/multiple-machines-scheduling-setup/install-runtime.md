---
title: Installation of Test Studio Components
page_title: Installation of Test Studio Components
description: "Install Test Studio Services and Run-time on execution machines and setup machines for remote scheduled execution. Which machine should host the Test Studio Services? Do I need more than one machine with the Test Studio Services."
position: 0
---
# Install Test Studio Across the Machines

The Scheduling setup in Test Studio is a set of services, which allows the communication between the Test Studio components on the different machines. Depending on their role in the configuration, the machines can run different editions of the product, and can be set up in various combinations.

This article will guide you through the options of possible configurations.

> __Important__
> <br>
> <br>
> Test Studio installation must be configured from a Windows Administrator account.

## Scheduling Components

The <a href="/automated-tests/scheduling/overview#which-are-the-scheduling-setup-components" target="_blank">Test Studio Scheduling components</a> are the Test Studio services and these need to be installed and configured on one of the machines, which will be used in the setup as a Scheduling and Storage server. Depending on the decision which machine will host which component, you can:

- Add the Test Studio Services by <a href="/prerequisites/installation/add-services#trigger-a-change-of-the-installation" target="_blank">changing the default standalone installation</a>. (The services are not included by default in the <a href="/test-studio-editions#test-studio-standalone-application" target="_blank">Test Studio standalone installation</a>).
- Install the default <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-time edition</a>. (The services are included in the default Run-time installation. If necessary, the installation can be modified to not include these.)

## Execution Servers

An Execution Server can be any physical or virtual machine with __minimum installation of the <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-time edition</a>__. Multiple Execution Servers can be connected to a single Scheduling Server to allow you execute multiple test lists simultaneously. Differences in operating systems and browsers between the machines running on the Scheduler and the Execution servers are allowed.

> __Important__
> <br>
> <br>
> Each Execution Server must be running the same version of Test Studio as the Scheduling Server.

To register an Execution Server to the Scheduling service, you need to <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server" target="_blank">configure its Execution client to point to the running Scheduling service</a> in the setup. The Execution client is part of each Test Studio installation - the Standalone, or Run-time.

### Specific Requirements for an Execution Server Machine

Few things to consider when choosing an Execution Server machine:

- Ensure that the Execution Server machine has sufficient disk space to store a copy of the project you schedule test lists from.
- An active and unlocked user session is required to execute UI tests successfully. There are <a href="/knowledge-base/test-execution-kb/locked-machine#solution" target="_blank">possible configurations and workarounds</a> to help in setting up the Execution machines to keep the active session.
- An exception from the last requirement is executing tests in Chrome headless mode - it only requires a logged user on the Execution machine.
- If you plan to use 'Get Latest from TFS' on scheduled test runs, make sure the Test Studio Execution Server is running under an account with access to log on to the TFS repository.

[1]: /img/features/scheduling-test-runs/install-runtime/fig1.png
[2]: /img/features/scheduling-test-runs/install-runtime/fig2.png
[3]: /img/features/scheduling-test-runs/install-runtime/fig3.png
[4]: /img/features/scheduling-test-runs/install-runtime/fig4.png
[5]: /img/features/scheduling-test-runs/install-runtime/fig5.png
[6]: /img/features/scheduling-test-runs/install-runtime/fig6.png
[7]: /img/features/scheduling-test-runs/install-runtime/fig7.png
[8]: /img/features/scheduling-test-runs/install-runtime/fig8.png