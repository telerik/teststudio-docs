---
title: ExecuteCommand failed! Protocol error Promise was collected 
description: This article provides troubleshooting steps for resolving the "ExecuteCommand failed! InError set by the client. Client Error Protocol error (Runtime.evaluate) Promise was collected" error in Telerik Test Studio.
type: troubleshooting
page_title: How to troubleshoot "ExecuteCommand failed! Promise was collected" error 
slug: troubleshoot-execute-command-failed-error-telerik-test-studio
tags: troubleshooting, executecommand error, client error, protocol error, runtime.evaluate error, Telerik Test Studio

---
## Description
I encounter the following error when executing an automation script in Telerik Test Studio:

```
'ExecuteCommand failed! InError set by the client. Client Error: Protocol error (Runtime.evaluate): Promise was collected BrowserCommand'
```

This error occurs on a click step which clicks on a button that opens a new screen. While the button is clicked and the new screen is displayed, the step fails.

## Cause
The cause of this error is currently unknown and difficult to reproduce. It has been reported by multiple customers but has not been replicated on our end.

## Solution
To troubleshoot this issue, please try the following steps:

1. Ensure that you are using the latest version of Telerik Test Studio. If not, upgrade to the latest version and rerun the test to check if the error persists.

2. If the error still occurs, open the properties of the failing click step and uncheck the checkbox for the 'SimulateRealClick' property. Run the test again and observe the outcome.

If the issue persists after trying these steps, further troubleshooting may be required so consider <a href="/features/test-runners/artoftest-runner" target="_blank">submitting a support thread</a> with sending the complete failure logs for the specific failing test you work on. You can use the __Export__ button from the <a href="/automated-tests/test-results/step-failure-details#failure-reason-section" target="_blank">Step Failure Details section</a>. 
