---
title: Stop or Cancel a Scheduled Job
page_title: Stop or Cancel a Scheduled Job
description: "Test Studio Stop or Cancel a Scheduled Job"
position: 10
---
# Stop or Cancel a Scheduled Job

There are a few ways to stop or cancel a scheduled job once it has been submitted.

1.&nbsp; In the Results tab when you hover over a scheduled job, a small X button appears. After clicking that Test Studio will prompt you for deleting the scheduled job.

<table id="no-table">
<tr>
<td>![X button][1]</td>
<td>![Delete Series][2]</td>
</tr>
<table>

2.&nbsp; The scheduled job is actually a file on the disk on the machine which is hosting the scheduling server. Just find and delete the file.

- If you are running it locally, it will be located by default at **C:\Users\<yourUserName>\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage** 

- If you are running it remotely, you have to look at the service account at

   	**C:\Windows\System32\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage** for 32-bit machines

   	or

   	**C:\Windows\SysWOW64\config\systemprofile\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage** for 64-bit machines.

3.&nbsp; The service itself is a REST Web Service. If you are familiar with <a href="http://www.telerik.com/fiddler" target="_blank">Fiddler's</a> Composer tab you can send a delete call to **http://<yourserver>:8009/Jobs/<jobId>**. In order to get the job ID, send a GET request to **http://<yourserver>:8009/Jobs/**

![GET Request][3]

*Send GET request to the scheduling server*

![GET ID][4]

*Get the ID of the scheduled job*

![Delete][5]

*Delete the scheduled job*

[1]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig1.png
[2]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig2.png
[3]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig3.png
[4]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig4.png
[5]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig5.png
