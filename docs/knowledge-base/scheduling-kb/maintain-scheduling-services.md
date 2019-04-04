---
title: Maintain Scheduling Services
page_title: Maintain Scheduling Services
description: Restart Telerik Scheduling and Storage Services. The Scheduling setup is stuck or hanged and no scheduled tests or test lists can be executed. 
position: 1
---

# Maintain Scheduling Services

## Restart Scheduling and Storage Services

If multiple jobs stuck to the Schedule server and it does not work and no test lists could be executed remotely restarting the scheduling services might solve the issue. 

Exit Test Studio and ensure all its processes are stopped in the Task Manager. Open Windows Services and find the Telerik Scheduling and Telerik Storage Services and restart them. 

![Windows Services][1]

## Config files

The Scheduling config file is generated automatically during the initial Scheduling setup. Its default location is *C:\ProgramData\Telerik\Configs* and its name is ***Telerik.TestStudio.Scheduling.Client.exe.config***. Opened in a text editor it looks similar to this: 

![Config File][2]

In some rare cases it might become corrupted and to prevent the Scheduling service to execute successfully. If the file is missing it will be automatically recreated to its default values once Test Studio is started. Therefore if an issue is identified with the Config file it is recommended to simply delete it. 

## Reinstall Scheduling and Storage Services

The Scheduling and Storage services could be re-installed from Test Studio installation wizard. Close Test Studio and terminate all its processes. Open Control Panel and navigate to the Change icon once Progress Test Studio is selected. Both services could be accessed in the **Customize Installation Dialog**. If it is required you could uninstall and then install them again. 

![Re-install Services][3]


[1]: /img/knowledge-base/scheduling-kb/maintain-scheduling-services/Services_fig1.jpg
[2]: /img/knowledge-base/scheduling-kb/maintain-scheduling-services/ConfigFile_fig2.png
[3]: /img/knowledge-base/scheduling-kb/maintain-scheduling-services/fig3.png
