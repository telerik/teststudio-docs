---
title: WPF Tests
page_title: Configure WPF Test
description: "Configure WPF Test (Standalone) in Test Studio for specific APF application. Create a WPF test in Test Studio and record"
position: 1
---
# WPF Tests in Test Studio

With Test Studio you can record and execute tests against any WPF desktop application. In order to specify the application, which will be tested, you need to configure the WPF test and point to the executable file of the WPF app.

This article will guide you through the WPF test configuration process.

## Configure WPF Test to Record the Specific Application

The __configuration of the WPF test requires an executable file of a valid WPF app to be specified__ and, thus,  used for recording and execution. When you open a WPF test in Test Studio, you will notice that some of the options in the __Test__ ribbon are different than these for a web test. The __Configure__ button replaces the browser control and timeouts options.

![Configure button](/img/automated-tests/recording/overview/fig10.png)

Click the __Configure__ button to open the __WPF Config Wizard__.

![WPF Config Wizard][1]

> **Tip**
> <br>
> <br>
> If you attempt to initiate a recording session in WPF test, before it is configured, the __WPF Config Wizard__ will popup and let you provide the necessary details.

## Choose the Application to Automate

Test Studio provides few options to define the application to automate - you can __browse to the folder__, where the executable file is located; or if the application is started, you can directly __select it from the list of active apps__.

![Specify path to WPF app][2]

The __WPF Application Path__ field allows you to drag and drop the application's shortcut icon into it, or click _Browse_ and locate it manually in File Explorer. 

![Browse path to WPF app][3]

The __Active WPF Applications__ list displays all WPF apps currently running and detected by Test Studio. Click on the desired one and hit the  __Select Application__ button and this will populate automatically the path to the executable file in the __WPF Application Path__ field.

![Select running WPF app][4]

Once an executable file is selected, the __WPF Application Path__ and __Current Path Expanded__ fields get populated accordingly. __WPF Application Path__ supports environment tokens (i.e. _%Program Files%\MyApp\App.exe_) and when using such, the __Current Path Expanded__ field displays the full path to the executable file. 

![Selected app and expanded path][5]

## Set Default WPF Application Path

The automation process requires multiple tests to be created for a single application. In such case configuring each created test will be a tedious task. Therefore Test Studio allows you to __set a default WPF app path on project level__ and use this for all WPF tests. The option is available in <a href="/features/project-settings/general" target="_blank">Project Settings -> General</a> and once a __Default Path is set__ each new WPF test in the project will be configured to use it.

![Use default path][6]

## Record Application Window State

For WPF tests you can choose whether to record the changes in the application window state - __Minimize, Maximize, Restore__ and __Close__ actions can be captured automatically in the recording process. If the recording scenarios require to interact with the window state, you can enable the checkbox under the __Recording Options__ section in the __Config Wizard__.

![record the changes in the application window state][7]

> **Note**
> <br>
> <br>
> Recording the changes in the application window state is a __setting on project level__. So, if it is enabled for one test in the project, it will be also applied for all existing and newly created WPF tests in the project.

## Finish WPF Test Configuration

Once you applied all necessary settings, you can __confirm the configuration__ by pressing the __OK__ button. Then, when you hit the <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">__Record__ button</a>, the configured WPF application will be launched and the recorder will be attached to it, so you can proceed with recording the test scenario.

> **Tip**
> <br>
> <br>
> In any case, when you need to change the applied settings, hit the __Configure__ button to access the wizard again.

[1]: /img/general-information/create-test-standalone/wpf-test/fig1.png
[2]: /img/general-information/create-test-standalone/wpf-test/fig2.png
[3]: /img/general-information/create-test-standalone/wpf-test/fig3.png
[4]: /img/general-information/create-test-standalone/wpf-test/fig4.png
[5]: /img/general-information/create-test-standalone/wpf-test/fig5.png
[6]: /img/general-information/create-test-standalone/wpf-test/fig6.png
[7]: /img/general-information/create-test-standalone/wpf-test/fig7.png
