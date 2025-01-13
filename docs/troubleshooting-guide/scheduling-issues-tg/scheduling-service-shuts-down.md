---
title: Scheduling Service Shuts Down
page_title: Scheduling Service Shuts Down
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: false
---
# Scheduling Service Shuts Down


## PROBLEM

The scheduling service will start, but after about 60 seconds it shuts back down. Looking at the Windows event log using the <a href="https://www.microsoftpressstore.com/articles/article.aspx?p=2467489&seqNum=2" target="_blank">Event Viewer</a> reveals:

<pre>
Application: Telerik.TestStudio.ExecutionManagerService.exe
Framework Version: v4.0.30319
Description: The process was terminated due to an unhandled exception.
Exception Info: System.IO.DirectoryNotFoundException
</pre>

## SOLUTION

Such behavior could be caused by unfinished scheduled jobs located in the job storage folder. The solution is to manually delete these files from:

- If the Scheduling Service is running as a service on a 32 bit machine:

    *C:\Windows\System32\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage*


- If the Scheduling Service is running as a service on a 64 bit machine:

    *C:\Windows\Syswow64\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage*


- If the Scheduling Service is running as a user:

    *%appdata%\Telerik\TestStudio\Scheduler\ScheduleStorage* 


Then restart the Telerik Scheduling and Storage services as described <a href="/knowledge-base/scheduling-kb/maintain-scheduling-services" target="_blank">here</a>.

If this still does not resolve the issue, there is a possibility the scheduling configuration file *Telerik.TestStudio.Scheduling.Client.exe.config* is corrupted. Find it in the folder *C:\ProgramData\Telerik\Configs* and delete it. Once Test Studio is restarted the file will be generated with default configurations.

![Scheduling Config][1]

[1]: /img/troubleshooting-guide/scheduling-issues-tg/scheduling-service-shuts-down/fig1.png

