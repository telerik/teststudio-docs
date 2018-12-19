---
title: Error Starting Services
page_title: Error Starting Services
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---

# Error Starting Services

## PROBLEM

While upgrading to Test Studio, this message appears:

**Service 'Telerik Scheduling Service' (Telerik Scheduling Service) failed to start. Verify that you have sufficient privileges to start system services.**

## SOLUTION 1:

It is very likely port: 8009 to be used by another application. This can be verified using <a href="http://windows.microsoft.com/en-us/windows/what-information-event-logs-event-viewer#1TC=windows-7" target="_blank">Event Viewer</a>. If this is the case:

1.&nbsp; Navigate to: **C:\ProgramData\Telerik\Configs**.

2.&nbsp;  Open **Telerik.TestStudio.ExecutionManager.exe.config** in text editor such as Notepad.

3.&nbsp; Change the port (the highlighted part) to something else, for example 8010. Save your changes and continue with installation.

![Change port][1]

## SOLUTION 2:


1.&nbsp; Cancel your Test Studio installation.

2.&nbsp; Uninstall the old version of Test Studio.

3.&nbsp; Open the Progress Test Studio Configs folder (C:\ProgramData\Telerik\Configs in Windows 7; C:\Documents and Settings\All Users\Application Data\Telerik\Configs in Windows XP). This is a hidden folder.

4.&nbsp; Rename the Execution Manager configuration file (Telerik.TestStudio.ExecutionManager.exe.config.xml) to a backup name (for example, Telerik.TestStudio.ExecutionManager.exe.config.xml.bak).

5.&nbsp; Restart the installation.

[1]: /img/troubleshooting-guide/installation-problems-tg/error-starting-services/fig1.png

