---
title: Unscheduled Test Runs
page_title: Unscheduled Test Runs
description: "Resolve issues with unscheduled or repeatedly running test lists in Test Studio. Learn how to clear scheduled jobs, restart the Scheduling service, and ensure accurate test execution and reporting."
position: 1
---
# Unscheduled Test Runs

## PROBLEM

A test list runs repeatedly, but does not appear in the Results view.


## SOLUTION

To solve such misbehavior remove manually the scheduled jobs stored on the machine which acts as the Scheduling Server. The scheduled run jobs are stored as files in the Scheduling service directory and the easiest way to address the misbehavior is to delete all files in the respective folder. Then restart the Scheduling service. 

The location of the Scheduling service directory depends on your configuration:


- If you are using the scheduling configuration with installed Test Studio Services, you have to look at the service account folder at: 

__C:\Windows\ServiceProfiles\LocalService\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage__

- If you are using the local setup, by default it will be located at: 
 
__C:\Users\\\<yourUserName>\AppData\Roaming\Telerik\TestStudio\Scheduler\ScheduleStorage__


>**Note:** 
> <br>
> Deleting all of the files in that folder will remove all scheduled jobs from your scheduling server!


