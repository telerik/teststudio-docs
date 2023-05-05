---
title: Unscheduled Test Runs
page_title: Unscheduled Test Runs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Unscheduled Test Runs

## PROBLEM

A test list runs repeatedly, but does not appear in the Results view.

## PROBLEM

The scheduling service will start, but after about 60 seconds it shuts back down. Looking at the Windows event log  in the <a href="https://www.microsoftpressstore.com/articles/article.aspx?p=2467489&seqNum=2" target="_blank">Event Viewer</a> reveals:

<pre>
Application: Telerik.TestStudio.ExecutionManagerService.exe
Framework Version: v4.0.30319
Description: The process was terminated due to an unhandled exception.
Exception Info: System.IO.DirectoryNotFoundException
</pre>

## SOLUTION

To solve such misbehavior remove manually the scheduled jobs stored on the machine which hosts the Scheduling Server. The scheduled run jobs are stored as files in the ScheduleStorage directory and the easiest way is to delete all these in the respective folder. 

The location of the ScheduleStorage directory depends on your configuration:

- If the Scheduling Service is running as a service on a 32 bit machine:

    *C:\Windows\System32\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage*


- If the Scheduling Service is running as a service on a 64 bit machine:

    *C:\Windows\Syswow64\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage*


- If the Scheduling Service is running as a user:

    *%appdata%\Telerik\TestStudio\Scheduler\ScheduleStorage* 

>**Note:** Deleting all of the files in the respective folder will remove all scheduled jobs from your scheduling server!