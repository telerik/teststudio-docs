---
title: Error Starting Services
page_title: Error Starting Services
description: "Test Studio installation error Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services. How to resolve Test Studio Scheduling service not starting during the installation of the tool"
position: 1

---

# Error Starting Services

## Problem

While upgrading Test Studio installation I get a message like this:

`Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services.`

## Cause

This error may appear if the default port used for the Scheduling service - 8009, is used by another application. This can be verified using the <a href="https://learn.microsoft.com/en-us/shows/inside/event-viewer" target="_blank"> Windows Event Viewer</a>. 

## Solution 1:

1. Cancel the current Test Studio installation.

1. Open a File Explorer and browse to: `C:\ProgramData\Telerik\Configs`.

1. Locate file with name `Telerik.TestStudio.ExecutionManager.exe.config` and open it in a text editor app such as Notepad++.

1. Change the port (highlighted in the image below) to another port - for example 8010. Save the changes and continue with installation.

    ![Change port][1]

1. Restart the installation.

## Solution 2:


1. Cancel the current Test Studio installation.

1. Uninstall the old version of Test Studio through the Windows Control Panel -> Programs and Features.

1. Open a File explorer and browse to the Progress Test Studio folder with config files `C:\ProgramData\Telerik\Configs`. 

    > __Note__ 'ProgramData' is a Windows system folder and is hidden by default. You my need to change the Windows File Explorer settings to show all files. 

2. Locate file with name `Telerik.TestStudio.ExecutionManager.exe.config` and to a backup name - for example `Telerik.TestStudio.ExecutionManager.exe.config.bak`. This will cause the installation process to create a new config file with the default settings for the Scheduling configuration. 

3. Restart the installation.

[1]: /img/troubleshooting-guide/installation-problems-tg/error-starting-services/fig1.png

