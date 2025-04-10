---
title: Stop or Cancel a Scheduled Job
page_title: Stop or Cancel a Scheduled Job
description: "Test Studio Stop or Cancel a Scheduled Job"
position: 10
---
# Stop or Cancel a Scheduled Job

Once you have <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#configure-the-test-studio-scheduling-service" target="_blank">configured your Scheduling setup</a> with at least one execution machine connected and your current <a href="/features/scheduling-test-runs/connect-to-scheduling-server#schedule-tests-on-remote-execution-machines" target="_blank">project is connected to the Scheduling service</a>, you can proceed with <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">scheduling test lists</a>.

If a test list is scheduled to be executed any time in the future or is set for recurring runs, you may need to cancel the upcoming execution. There are a few ways to stop or cancel a scheduled job, once it has been submitted.

## Delete an Upcoming Scheduled Test List from Calendar

In the Results tab when you hover over a scheduled job, a small X button appears. After clicking that Test Studio will prompt you for deleting the scheduled job.

<table id="no-table" style="border:none;">
<tr style="text-align: center; background-color: transparent; border:none;">
<td>

![X button][1]</td>
<td>

![Delete Series][2]</td>
</tr>
</table>

## Delete the Physical File That Represents the Scheduled Job

Each scheduled job is represented as a file on the disk. These files are stored on the machine which is hosting the Scheduling service. If it happens that the scheduled job doesn't appear in the Results tab you can delete the physical file. 

- If you are using the local setup, by default it will be located at: 
 
__C:\Users\\\<yourUserName>\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage__


- If you are using the scheduling configuration with installed Test Studio Services, you have to look at the service account folder at: 

__C:\Windows\ServiceProfiles\LocalService\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage__


[1]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig1.png
[2]: /img/features/scheduling-test-runs/stop-cancel-scheduled-job/fig2.png
