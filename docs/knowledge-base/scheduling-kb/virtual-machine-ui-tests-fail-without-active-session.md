---
title: UI Testing on Virtual Machines Fails Without Active User Session
description: Resolving issues with Telerik Test Studio UI testing in virtual machines when no active user session exists.
type: troubleshooting
page_title: Virtual Machine UI Tests Fail Without Active Session in Telerik Test Studio
meta_title: Virtual Machine UI Tests Fail Without Active Session in Telerik Test Studio
slug: virtual-machine-ui-tests-fail-without-active-session
tags: telerik test studio, ui testing, virtual machine, vgpu, session monitor
res_type: kb
ticketid: 1698547
---
# Test Studio UI Testing on Virtual Machines Fails Without Active User Session

## Description

I run UI test scripts in a virtual machine using vGPU with Telerik Test Studio. These scripts are triggered by a pipeline, and no user interacts with the virtual machine during execution. However, the __tests fail to detect or interact with elements__ like login fields, despite the application launching successfully. When I establish an RDP connection to the virtual machine, the tests execute correctly.

## Cause

__UI functional testing requires an active user session__ to interact with UI elements effectively. When the virtual machine lacks an active session, the tests fail to interact with the application as expected. Establishing an RDP session temporarily resolves the issue because it restores the active console session.

## Solution

To ensure UI test execution without requiring a continuous RDP session, use the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#user-session-configuration" target="_blank">Test Studio Session Monitor application</a>. This tool maintains an active user session by reconnecting the console session after the RDP connection closes.

## Steps to Resolve the Misbehavior

1. Ensure the Test Studio Session Monitor is installed and enabled on the virtual machine.
2. Leave the Session Monitor application running on the virtual machine.
3. Disconnect the RDP session safely, knowing that the console session will be restored by the Session Monitor.
4. Trigger the test scripts from the pipeline. The tests should execute successfully as the active session is maintained.

If the Session Monitor has been enabled but the issue persists, consider alternative remote desktop software that ensures the virtual machine maintains an active session during pipeline-triggered executions.

## See Also
- [User Session Configuration for Execution Server](https://docs.telerik.com/teststudio/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#user-session-configuration) 
- [Test Studio Execution Servers Overview](https://docs.telerik.com/teststudio/automated-tests/scheduling/multiple-machines-scheduling-setup) 
