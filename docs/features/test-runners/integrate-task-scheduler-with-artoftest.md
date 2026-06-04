---
title: Integrate Windows Task Scheduler with ArtOfTest.Runner
page_title: Integrate Windows Task Scheduler with ArtOfTest.Runner
description: "Test Studio can integrate the command line runner ArtOfTest.Runner with Windows Task Scheduler "
position: 1
---
# Integrate Windows Task Scheduler with ArtOfTest.Runner

1. Create a test project and put into a location (shared) which can be accessed from the execution machine.

2. Create a *.bat file which copy the project from the shared location to execution machine and run the list.

![bat file](/img/features/test-runners/integrate-task-scheduler-with-artoftest/fig1.png)

3. Create a <a href="http://windows.microsoft.com/en-au/windows/schedule-task#1TC=windows-7" target="_blank">Basic Task in Windows Task Scheduler</a> to run the already created bat file.

* Click the Action menu, and then click **Create Basic Task**.
 
![basics task](/img/features/test-runners/integrate-task-scheduler-with-artoftest/fig2.png)

* Type a name for the task and an optional description, and then click Next.

![task name](/img/features/test-runners/integrate-task-scheduler-with-artoftest/fig3.png)

* Select a schedule based on the calendar.

* To schedule a program to start automatically, click **Start a program** under Action, and then click Next.

* Click **Browse** to find the bat file you want to start, and then click Next.

* Click **Finish**.

Windows Task Scheduler will run the .bat file in the selected time. 

> OnBeforeTestListStarted and OnAfterTestListCompleted methods will be called accordingly.

