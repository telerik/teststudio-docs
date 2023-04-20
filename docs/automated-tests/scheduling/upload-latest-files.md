---
title: Upload To Storage
page_title: Upload Latest Project Files
description: You have recurring test list scheduled and you need to make some change in the test list such as editing a particular test case, add or remove tests etc. You can force uploading the changes to the database
position: 7
---
# Upload Latest Project Files to Storage Database

The __Upload__ function allows you to upload any recent changes in project files of a connected to Scheduling project to the Storage database. This way you can control what state of files is then delivered to the execution machines.

This article describes the details about maintaining project files state in the Storage database.

## Upload Button

The __Storage service__ and underlying database keep the project files which gets deployed to the execution machines for a scheduled or remote test list run. The __Upload__ button gets enabled when the <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">project you work on is connected to a Scheduling service</a>.

![Upload to storage button](/img/automated-tests/scheduling/upload/fig1.png)

Whenever you apply any change in the tests, elements or test list, the __Upload__ button gets marked with a yellow exclamation mark to remind that local project state is different from the project state in the Storage database.

![Pending Upload to storage button](/img/automated-tests/scheduling/upload/fig2.png)

> __Tip__
> <br>
> <br>
> Maintaining the upload to storage database manually allows you to __keep the project files in the database in a clean working state__. That way you can ensure the __remote test runs use a working tests version__ and lets you continue developing new tests independently from scheduled jobs.
> <br>
> This is extremely useful in the cases when multiple team members work on the same project in source control environment and are using different branches.

## Close Project with Pending Recent Changes Not Uploaded

When closing a project, which local state is different from the files in the Storage database, a message pops up and lets you choose whether you want to upload recent changes to the Storage, or you want to keep these only locally.

![Prompt to Upload to storage](/img/automated-tests/scheduling/upload/fig3.png)

If you choose to not upload the latest changes, the __Upload__ button keeps these pending when you open the project again.

## Recurring Test List Files Upload of Recent Changes

For any upcoming scheduled job, including recurring test list runs, you can use the option to upload the latest files related to its tests - go to the __Results__ tab in Test Studio, right click on the scheduled run and select **Upload latest project files**.

![ Scheduled test list Upload latest project files](/img/automated-tests/scheduling/upload/fig0.png)
