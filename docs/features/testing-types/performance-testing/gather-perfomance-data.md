---
title: Gather Performance Data
page_title: Gather Performance Data
description: "Gather Performance Data from performance test run in Test Studio."
previous_url: /user-guide/performance/gather-performance-data.aspx, /user-guide/performance/gather-performance-data
position: 2
---
# Gather Performance Data

> The target machine to be monitored must have either <a href="/general-information/test-studio-run-time" target="_blank">**Run Time edition**</a> or Test Studio installed on it. The <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">execution server</a> needs to be running before Test Studio can connect to it for performance monitoring.

1.&nbsp; Click the Performance tab.

2.&nbsp; Read the **Introduction** to Performance Testing.

![Introduction][1]

3.&nbsp; Click **Get Started** to continue. 

4.&nbsp; Ensure you have a valid automated test candidate loaded for the Performance Run.

5.&nbsp; Click the **Configure** button under section **2: Set Up**.

![Set Up][2]

6.&nbsp; Set the location to save the results under section **1: Specify Save Results Folder**.

![Results folder][3]

> To gather additional Performance Counter data, continue to step 7. If not, skip to step 8. 

7.&nbsp; Click Continue to Step 2. Under section 2: **Gather Performance Counter Data**:

a. Check the **Gather Computer Performance Data** box.

b. Click the **Add a computer** button.

![Add a computer][4]

c. Set a friendly name for this server configuration, then enter the actual machine name or IP address. The machine must be running the Test Studio Profiling Service.

d. Click the **Connect** button to confirm a connection can be established. 

![Connect][5]

e. If the validation fails, go to the **Help** tab and click the **View Log** button in the **Logging** ribbon. The **Enable** button must be selected beforehand for the log to populate with information. 

![View Log][6]

>  Note: The most common reason for a validation failure is that the Profiler Service is not running on the computer you entered. That computer must have <a href="/general-information/test-studio-run-time" target="_blank">Run-Time Edition</a> installed. You can check by showing the Test Studio Test Runner from that machine's System Tray. 

![Test Runner][7]

f. Move below to the section labeled **Select the system resources that you want to monitor**.
g. Choose from the Available Counters. Select an entire group, or expand the group to select specific counters within it.

![Available Counters][8]

> It is up to you and your developers to decide which Performance Counters to use for your application. The selections made above were chosen for demonstration purposes. See here for more information.

h. To import a previously saved template of performance counters, click ![Folder][9] .

![Saved template][10]

Select the template you wish to use. You can view the performance counters included in this template. Click add to use this template.

![Add Template][11]

i. To save this set of performance counters as a template, click ![Disk][12].

![Save New Template][13]

j. Click **Done Editing** when finished. Click **Cancel** to revert changes. Click **Delete** to remove this server configuration.

k. Click the **Add a computer** button to gather performance data on multiple machines.

l. Click **Save** when finished.

8.&nbsp; Click the **Quick Run** button under section **3: Quick Performance Run**. 

![Run][14]

9.&nbsp; To make configuration changes before your next Performance Run, click the **Configure** button in the **Set Up** ribbon.

![configure][15]

10.&nbsp; To execute your next Performance Run, select a browser type and click Run in the Quick Performance Run ribbon.

![Run][16]

[1]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig1.png
[2]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig2.png
[3]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig3.png
[4]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig4.png
[5]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig5.png
[6]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig6.png
[7]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig7.png
[8]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig8.png
[9]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig9.png
[10]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig10.png
[11]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig11.png
[12]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig12.png
[13]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig13.png
[14]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig14.png
[15]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig15.png
[16]: /img/features/testing-types/performance-testing/gather-perfomance-data/fig16.png