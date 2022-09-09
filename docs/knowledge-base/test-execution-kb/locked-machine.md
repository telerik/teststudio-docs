---
title: Execution on Locked Machine
page_title: Execution on Locked Machine
description: "Test Script Execution on Locked Machine. Test Studio test run with error SendInput: Failed. Win32Error. If disconnect from and/or lock the machine that acts as Execution Server, no scheduled tests are executed. This includes Remote Desktop Sessions that are minimized or closed. The following error may appear for tests with dialog handling - UnsupportedNonInteractiveOperationException. Test Studio test run with error SendInput: Failed. Win32Error" 
previous_url: /user-guide/knowledge-base/test-execution/no-tests-execute-on-locked-machine.aspx, /user-guide/knowledge-base/test-execution/no-tests-execute-on-locked-machine
position: 1
---
# No Tests Execute on Locked Machine #

## Problem ##

When I disconnect from and/or lock the machine that acts as my <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">Execution Server</a>, no scheduled tests are executed. This includes Remote Desktop Sessions that are minimized or closed. The following error may appear for tests with dialog handling steps or type and click steps, which are using *'SimulateRealTyping'* or *'SimulateRealClick'* properties enabled: 

```
UnsupportedNonInteractiveOperationException(additional information about the exception)
```

or 

```
SendInput: Failed. Win32Error:
InnerException:
System.ComponentModel.Win32Exception (0x80004005): SendInput: Failed. Win32Error:
```

Is it possible for tests to execute normally without requiring my account to always be logged in on that machine?

## Solution ##

Any test that requires **moving the mouse** or sending **key strokes** requires an unlocked desktop - also dialog handling uses both. Telerik tests are not the only types affected by this Windows limitation, you will find this is a general problem with any tool that performs UI testing.

Our tests against HTML-based web applications frequently can work on a locked machine because most test steps don't use the mouse or keyboard. Instead they are able to inject Click or Select events against the element in question (e.g. a button or drop-down select). Unfortunately Silverlight and WPF applications do not allow us to inject these events. We have to simulate system wide mouse moves, clicks, and key presses instead.

### Minimum Requirements for a Test Studio Execution Machine ###

Ensure all the following conditions are met for the server on which the tests will be executed:

* Test agent is running as an interactive process and not as a service (you must specify a user name and password for the agent to log on).

* There is an active logon session on the test server for the user mentioned above.

* The test server is not locked, on standby, nor hibernated when the test executes.

* Browser is not minimized during test execution.

### Test Studio Built-in Options to Control the User Session ###

The Test Studio Execution client provides <a href="/features/scheduling-test-runs/create-execution-server#user-session-configuration" target="_blank">built-in options to control the User session</a> on the remote execution machines. Enabling both <a href="/features/scheduling-test-runs/create-execution-server#keep-machine-awake" target="_blank">__Keep Machine Awake__</a> and <a href="/features/scheduling-test-runs/create-execution-server#reconnect-to-console-on-disconnect" target="_blank">__Reconnect to Console on Disconnect__</a> will keep the machine active and unlocked when an unattended scheduled run is triggered.

> __Tip__
> <br>
> <br>
> <a href="/automated-tests/headless/headless-test-execution" target="_blank">Execution of tests against Chrome Headless mode</a> does not require active and unlocked session. Though, it __requires a user to be logged on__ the machine.

### Possible Workarounds ###

Some of our customers report success using the following workarounds:

* Use a <a href="http://en.wikipedia.org/wiki/Virtual_Network_Computing" target="_blank">VNC</a> product. With this they remotely connect to the test machine, leave the user logged on, but disconnect the VNC connection. This leaves the Windows session open and unlocked, but humans still cannot access it without reconnecting the VNC connection (which usually means re-authenticating).

* <a href="/knowledge-base/scheduling-kb/keep-active-session" target="_blank">Keep an Active Session Running</a> on the server.

* Set registry keys to work with a <a href="/knowledge-base/test-execution-kb/minimized-rdc" target="_blank">Minimized Remote Desktop Connection</a>.