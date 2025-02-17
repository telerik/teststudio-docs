---
title: Download Dialog Fails Due to Access Denied
page_title: Download/Upload Dialog Fails Due to Current User Does Not Have Access
description: "Handle Download/SaveFile Dialog step fails with message that current user doesn't have access to the folder specified in Handle download dialog step. Handle Upload/OpenFile dialog step fails with message that current user doesn't have access to the folder specified in Handle upload dialog step. Handling Download or Upload dialogs in Test Studio fails with System.UnauthorizedAccessException. Handling SaveFile or OpenFile dialogs in Test Studio fails with System.UnauthorizedAccessException  "
position: 1
---

# Download or Upload Dialog Handling Fails Due to Missing Permissions

## Issue

A web test with 'Handle Download dialog' or 'Handle Upload dialog' step fails with the following error message in the execution log. 
A WPF test with 'Handle OpenFile dialog' or 'Handle SaveFile dialog' step fails with the following error message in the execution log. 

```txt
Failure Information: 

The current user does not have access to this folder C:\workingStation\temp\noPermissionsFolder\myw3schoolsimage.jpg. 

You can use the %USERPROFILE%\Downloads\myw3schoolsimage.jpg folder instead or grant access to the folder on all executing machines. 

For more information: https://docs.telerik.com/teststudio/troubleshooting-guide/test-execution-problems-tg/download-dialog-access-denied

InnerException:
System.UnauthorizedAccessException: The current user does not have access to this folder C:\workingStation\temp\noPermissionsFolder\myw3schoolsimage.jpg. 

You can use the %USERPROFILE%\Downloads\myw3schoolsimage.jpg folder instead or grant access to the folder on all executing machines. 

For more information: https://docs.telerik.com/teststudio/troubleshooting-guide/test-execution-problems-tg/download-dialog-access-denied
```

![Failure details for upload or download dialog not handled](/img/troubleshooting-guide/test-execution-problems-tg/download-dialog-access-denied/failure-message.png)

## Cause

The error indicates that the current user running the test __does not have access or write permissions__ to the folder specified in the 'Handle Upload dialog' or 'Handle Download dialog' steps.

## Solution

You have two options to address the case:

* Contact your system administrator and request read/write access to the folder specified in the 'Handle Upload dialog' or 'Handle Download dialog' steps for web test, and the 'Handle OpenFile dialog' or 'Handle SaveFile dialog' steps for WPF test. 
* Modify the file path used in the 'Handle Upload dialog' or 'Handle Download dialog' steps for web test, and the 'Handle OpenFile dialog' or 'Handle SaveFile dialog' steps for WPF test, and replace it with a folder for which the current user has the proper permissions. 

 > __Tip!__
><br>
><br>
> Test Studio supports all <a href="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" target="_blank">recognized system variables</a> and we recommend using a proper one which defines a location accessible for any user executing the test in different environments. 
><br>
><br>
> For example, the __current Windows user folder can be defined using the Windows variable %USERPROFILE%__. 

