---
title: Scheduling Results
page_title: Scheduling Results
description: "Test Studio results from scheduled test runs. Scheduling Results. Scheduling calendar. "
position: 0
---
# Scheduling Results

The results generated from a scheduled or remote test list execution, similar to local test list execution, are stored on project level and displayed in the <a href="/automated-tests/test-list-results/calendar" target="_blank">__Results__</a> tab in Test Studio. The difference is that __these are stored in the database__ maintained from the Test Studio Storage Service.

Due to this specific there are few options in the __Results__ tab available, only if the <a href="/automated-tests/scheduling/remote-scheduled-run" target="_blank">Scheduling setup is configured for a project</a>.

## Publish To Server

This options allows you to populate any result from a <a href="/automated-tests/test-lists/test-list-execution" target="_blank">local test list run</a> to the Storage Service database. That way you will be able to see this result also in the <a href="/general-information/test-results/executive-dashboard" target="_blank">Executive Dashboard</a>. Choose any local test list run result and click the __Publish To Server__ button.

![Publish to Server][1]

If the run result is already populated in the storage database, there is a prompt message to confirm whether you need to republish this.

![Confirm re-Publish to Server][2]

> __Tip__
><br>
><br>
> You can select multiple consecutive results using __clicks + the *Shift* key__, or any multiple results using the __*Ctrl* key + clicks__, and publish these to the Storage Server.

## Manage Results

The **Manage Results** view provides a list of all scheduled and remote test list runs executed through the Scheduling server, for all different projects connected to the Scheduler. The details listed for each entry are the _test list name_, the _end_ and _start_ date and time and the _project name_. The local results uploaded to the database are also in this list.

![Manage Results][3]

From this list you can delete any test list run and this will delete the result file from the storage database. If this is a local run, which result was published to the storage, the local stored result remains in the _Results_ project sub-folder and, thus, in the __Results__ tab in Test Studio project.

![Delete Results][4]

> __Tip__
><br>
><br>
> In this list you can select multiple consecutive results using __clicks + the *Shift* key__, or any multiple results using the __*Ctrl* key + clicks__, and delete these from the Storage Server.

## Executive Dashboard

The <a href="/general-information/test-results/executive-dashboard" target="_blank">Executive Dashboard</a> is a tool, which allows __anyone in the team to explore the results from the scheduled test list execution__, even if they are not a real Test Studio user. The Dashboard is connected to the storage database and visualizes the results stored into it in the browser and on any device, which has access to it.

[1]: /img/automated-tests/scheduling-results/scheduling-results/fig1.png
[2]: /img/automated-tests/scheduling-results/scheduling-results/fig2.png
[3]: /img/automated-tests/scheduling-results/scheduling-results/fig3.png
[4]: /img/automated-tests/scheduling-results/scheduling-results/fig4.png
