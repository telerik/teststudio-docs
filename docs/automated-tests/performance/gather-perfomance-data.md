---
title: Gather Performance Data
page_title: Gather Performance Data
description: "Gather Performance Data Counters on the Execution machine during a performance test run in Test Studio."
position: 8
---
# Gather Performance Data

> The target machine to be monitored must have either <a href="/general-information/test-studio-run-time" target="_blank">**Run Time edition**</a> or Test Studio installed on it. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Test Studio Execution Client</a> needs to be running before Test Studio can connect to it for performance monitoring.

The below instruction assumes that you already have configured a performance run and you only need to add performance counters to be monitored. 

1. Click the **Configure** button in the **Set Up** ribbon.

    ![Click configure button][15]

2. Click **Continue to Step 2 >** button in the **Configure Performance Settings** window. 

    ![Continue to step 2](/img/features/testing-types/performance-testing/gather-perfomance-data/continue-to-step-2.png)

3. Check the **Gather Computer Performance Data** checkbox.

4. Click the **Add a computer** button.

    ![Add a computer][4]

5. Set a friendly name for this machine configuration, then enter the actual machine name or IP address. The machine must be running the Test Studio Profiling Service, e.g. the Test Studio Execution client.

6. Click the **Connect** button to confirm a connection can be established. 

    ![Connect][5]
    
    > __Tip__ 
    > <br> 
    > If the connection fails, go to the **Help** tab and click the **View Log** button in the **Logging** ribbon. The **Enable** button must be selected beforehand for the log to populate with information. If it is not useful for you, submit the generated log zipped into a support thread. 
    > <br> 
    > ![View Log][6]
    > <br>
    > <br>
    > __Note!__ The most common reason that the connection cannot be made is that the Profiler Service is not running on the computer you entered. That computer must have <a href="/general-information/test-studio-run-time" target="_blank">Run-Time Edition</a> installed and the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Test Studio Execution Client</a> running. 

7. In the section labeled **Select the system resources that you want to monitor** choose from the list with __Available Counters__. Select an entire group, or expand the group to select specific counters within it.

    ![Available Counters][8]

> __Note!__ 
> ><br>
> It is up to you and your team to decide which Performance Counters to use for your application depending on the monitoring you need. 


8. You can save this set of performance counters as a template, click ![Disk][12].

    ![Save New Template][13]

9. Click **Done Editing** when finished. Click **Cancel** to revert changes. Click **Delete** to remove this server configuration.

10. To import a previously saved template of performance counters, click ![Folder][9] .

    ![Saved template][10]

Select the template you wish to use. You can view the performance counters included in this template. Click __Add__ to use this template.

    ![Add Template][11]


11. You can monitor Performance Counters on more than one machine. Click the **Add a computer** button to gather performance data on another machine.

    ![Monitor multiple machines](/img/features/testing-types/performance-testing/gather-perfomance-data/monitor-multiple-machines.png)

12. When finished click **Save** and continue to initiating the performance test run. 

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
