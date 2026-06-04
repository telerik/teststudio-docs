---
title: ExecuteCommand failed! Protocol error Promise was collected 
description: This article provides troubleshooting steps for resolving the "ExecuteCommand failed! InError set by the client. Client Error Protocol error (Runtime.evaluate) Promise was collected" error in Telerik Test Studio.
type: troubleshooting
page_title: How to troubleshoot "ExecuteCommand failed! Promise was collected" error 
slug: troubleshoot-execute-command-failed-error-telerik-test-studio
tags: troubleshooting, executecommand error, client error, protocol error, runtime.evaluate error, Telerik Test Studio

---
## Description

I get the following error when executing an automation script in Telerik Test Studio:

````
'ExecuteCommand failed! InError set by the client. Client Error: Protocol error (Runtime.evaluate): Promise was collected BrowserCommand'
````

The error occurs on a click step. Although the button is clicked and the action is performed as expected, the step fails.

## Cause
The cause of the error is related to some mis-synchronization between the speed of executing the steps and the page responsiveness. 

## Solution
To troubleshoot this issue try the following steps:

1. Ensure that you are using the latest version of Telerik Test Studio. If not, upgrade to the latest version and rerun the test to check if the error persists.

2. If the error still occurs, open the <a href="/features/test-maintenance/test-step-properties" target="_blank">properties</a> of the failing click step and enable the `SimulateRealClick` property. Run the test again and observe the outcome.

3. If the test continues failing, revise the complete scenario and insert enough <a href="/features/recorder/highlighting-menu/quick-steps/wait" target="_blank">wait</a> and <a href="/features/recorder/highlighting-menu/quick-steps/quick-verification" target="_blank">verify</a> steps to ensure the state of the application before sending next actions. Optionally, you may also need to <a href="/teststudio/features/custom-steps/all-tests-common/execution-delay" target="_blank">add execution delays</a>. 

> **Tip**
><br> 
><br> Find out <a href="https://www.telerik.com/blogs/make-your-automated-tests-see-better-than-yourself" target="_blank">further useful examples for synchronizing the speed of executing the test steps to match the page responsiveness</a>. 

## See Also 

* <a href="https://www.telerik.com/blogs/make-your-automated-tests-see-better-than-yourself" target="_blank">How to make stable and always reliable tests</a>