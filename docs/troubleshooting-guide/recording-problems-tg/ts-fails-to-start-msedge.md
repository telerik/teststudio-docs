---
title: Test Studio Fails to Start Microsoft Edge Browser
page_title: Test Studio Fails to Start Microsoft Edge Browser
description: "Telerik Test Studio cannot start Microsoft Edge browser without browser extension."
position: 1
---
# Test Studio Fails to Start Microsoft Edge Browser

## PROBLEM

*Telerik Test Studio cannot start Microsoft Edge browser without browser extension. While Test Studio tests work fine with Chrome.*

    System.TimeoutException: This request operation sent to net.pipe://localhost/Telerik/TestingFramework.Hosts.Manager did not receive a reply within the configured timeout (00:01:00). The time allotted to this operation may have been a portion of a longer timeout. This may be because the service is still processing the operation or because the service was unable to send a reply message. Please consider increasing the operation timeout (by casting the channel/proxy to IContextChannel and setting the OperationTimeout property) and ensure that the service is able to connect to the client.

## SOLUTION

A possible reason for the issue can be a Windows Policy which disables Developer Tools in Edge browser. Try the following steps to resolve the error:

1. Open the registry editor. 
1. Check the registry node **"HKLM\SOFTWARE\Policies\Microsoft\Edge"** if it has the value of **"DeveloperToolsAvailability"** set to **REG_DWORD 2.**
1. Set the value to **REG_DWORD 0.** 


