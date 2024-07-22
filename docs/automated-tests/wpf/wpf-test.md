---
title: WPF Tests
page_title: Configure WPF Test
description: "Configure WPF Test (Standalone) in Test Studio for specific WPF application. Create a WPF test in Test Studio and record an automated scenario"
position: 1
---
# WPF Tests in Test Studio

Test Studio recording feature supports WPF applications built with .Net 4.5+ or .Net Core 3.1, and .Net 5 and above. To initiate recording session against specific application, you need to list its executable file in the WPF test.

This article guides you through the WPF test configuration process.

- [Configure WPF Test to Automate Specific App](#configure-wpf-test-to-record-specific-application)
- [Choose the Application to Automate](#choose-the-application-to-automate)
- [Record Application Window State](#record-application-window-state)
- [Finish WPF Test Configuration](#finish-wpf-test-configuration)

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/test-recorder-for-wpf-video-tutorial-test-studio" target="_blank">this video tutorial for recording an end-to-end WPF test scenario</a>.

## Configure WPF Test to Record Specific Application

The __configuration of the WPF test requires an executable file of a valid WPF app to be specified__ and, thus, used for recording and execution. When you open a WPF test in Test Studio, you can see the __Configure__ button in the __Test__ tools ribbon. Click the __Configure__ button to open the __WPF Config Wizard__.

![WPF Config Wizard][1]

> **Tip**
> <br>
> <br>
> If you attempt to initiate a recording session in WPF test, before it is configured, the __WPF Config Wizard__ pops up and lets you provide the necessary details.

## Choose the Application to Automate

Test Studio provides different options to define the application to automate: 

- [Specify an executable file](#configure-application-path-in-wpf-test); 
- [Use a default path](#set-default-wpf-application-path);
- [Select application from the list of active apps](#select-running-wpf-application);
- [Define startup arguments and working directory](#startup-arguments-and-working-folder-for-wpf-application)

![Specify path to WPF app][2]

## Configure Application Path in WPF Test

The __WPF Application Path__ field accepts drag and drop of the application's shortcut icon; Or use the __Browse__ button to locate the executable file manually in a File Explorer. 

![Browse path to WPF app][3]

__WPF Application Path__ field supports using environment tokens (such as `%Program Files%\MyApp\App.exe`). When using environment tokens, the __Current Path Expanded__ field displays the full path to the executable file. 

![Selected app and expanded path][5]

## Set Default WPF Application Path

The automation process requires multiple tests to be created for a single application. In such case configuring each created test will be a tedious task. The solution offered by Test Studio is to __set a default WPF app path on project level__ and use this for all WPF tests. 

The option is available in <a href="/features/project-settings/general" target="_blank">Project Settings -> General</a> and once a __Default Path is set__ each new WPF test in the project is configured to use it.

![Use default path][6]

## Select Running WPF Application

The __Active WPF Applications__ list displays all currently running WPF apps detected by Test Studio. Click on the desired one and hit the  __Select Application__ button and the path to the executable file in the __WPF Application Path__ field gets automatically populated.

![Select running WPF app][4]

## Startup Arguments and Working Folder for WPF Application

The configuration of a WPF application lets you set startup __Arguments__ and a __Working folder__ if these are required for the proper functioning of the tested WPF app. 

![Arguments and Working folder][5a]

## Record Application Window State

Test Studio lets you record the changes in the application window state - __Minimize, Maximize, Restore__ and __Close__ actions can be captured automatically while in the recording process. If the automation scenarios require to interact with the window state, enable the checkbox under the __Recording Options__ section in the __Config Wizard__.

![record the changes in the application window state][7]

> **Note**
> <br>
> <br>
> __Recording the changes in the application window state is a setting on project level__. So, once you enable it for one WPF test in the project, it is applied for all existing and newly created WPF tests in the current project.

## Finish WPF Test Configuration

Once you applied all necessary settings, __confirm the configuration__ by pressing the __OK__ button. Then, when you hit the <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">__Record__ button</a>, the configured WPF application is launched and the Test Studio recorder gets attached to it, so you can proceed with recording the test scenario.

> **Tip**
> <br>
> <br>
> In any case, when you need to change the applied settings, hit the __Configure__ button to access the wizard again.

## See Also:

* <a href="https://www.telerik.com/videos/teststudio/test-recorder-for-wpf-video-tutorial-test-studio" target="_blank">WPF Test Recording Video Tutorial</a>.

[1]: /img/general-information/create-test-standalone/wpf-test/fig1.png
[2]: /img/general-information/create-test-standalone/wpf-test/fig2.png
[3]: /img/general-information/create-test-standalone/wpf-test/fig3.png
[4]: /img/general-information/create-test-standalone/wpf-test/fig4.png
[5]: /img/general-information/create-test-standalone/wpf-test/fig5.png
[5a]: /img/general-information/create-test-standalone/wpf-test/fig5a.png
[6]: /img/general-information/create-test-standalone/wpf-test/fig6.png
[7]: /img/general-information/create-test-standalone/wpf-test/fig7.png
