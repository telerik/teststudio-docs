---
title: Desktop Tests
page_title: Configure Desktop Test
description: "Testing a desktop app with Test Studio. Configure Desktop Test (Standalone) in Test Studio for automating desktop application. Create a Desktop test in Test Studio and record an automated scenario for desktop app. "
position: 1
---
# Desktop Tests in Test Studio

Test Studio recording feature supports various desktop applications. To initiate recording session against specific application, you need to define which app to use in the desktop test.

This article guides you through the desktop test configuration process.

- [Configure Desktop Test to Record Specific Application](#configure-desktop-test-to-record-specific-application)
- [Choose the Desktop Application to Automate](#choose-the-desktop-application-to-automate)
- [Finish Desktop Test Configuration](#finish-desktop-test-configuration)

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">this video tutorial for recording an end-to-end Desktop test scenario</a>.

## Configure Desktop Test to Record Specific Application

The __configuration of the desktop test requires a desktop app to be specified__ and, thus, used for recording and execution. Open a Desktop test in Test Studio and find the __Configure__ button in the __Test__ tools ribbon. Click the __Configure__ button to open the __Desktop App Config Wizard__.

![Configure button](/img/automated-tests/desktop-testing/desktop-test/fig1.png)

> **Tip**
> <br>
> <br>
> If you try to initiate a recording session in a desktop test, before this is configured, the __Desktop Config Wizard__ pops up and lets you choose the application to automate.

## Choose the Desktop Application to Automate

Test Studio provides different options to define the application to automate: 

- [Specify an executable file](#configure-application-path-in-desktop-test) for this test;
- [Use a default path](#use-default-desktop-application-path) to the executable file set on project level;
- [Define startup arguments and working directory](#startup-arguments-and-working-folder-for-desktop-application)
- [Specify an Application User Model ID](#configure-application-user-model-id);
- [Choose to not launch an application](#do-not-launch-desktop-application)

![Config Desktop app wizard](/img/automated-tests/desktop-testing/desktop-test/fig2.png)

## Configure Application Path in Desktop Test

Click the __Browse__ button to open File Explorer and browse to the folder with the executable file and select it.

![Specify path to Desktop app](/img/automated-tests/desktop-testing/desktop-test/fig3.png)

The __Desktop Application Path__ field supports using environment tokens (such as `%Program Files%\MyApp\App.exe`). When using environment tokens, the __Full Path__ field displays the full path to the executable file. 

![Full application path](/img/automated-tests/desktop-testing/desktop-test/fig4.png)

## Use Default Desktop Application Path

The automation process requires multiple tests to be created for a single application. In such case configuring each created test will be a tedious task. Thus Test Studio allows you to __set a default desktop app path on project level__ and use this for all desktop tests. 

The option is available in <a href="/features/project-settings/general" target="_blank">Project Settings -> General</a> and once a __Default Desktop App is set__ each new Desktop test in the project is configured to use it.

![Use default path](/img/automated-tests/desktop-testing/desktop-test/fig5.png)

## Startup Arguments and Working Folder for Desktop Application

The configuration of a desktop application lets you set startup __Arguments__ and a __Working folder__ if these are required for the proper functioning of the tested app. 

![Arguments and Working folder](/img/automated-tests/desktop-testing/desktop-test/fig5a.png)

## Configure Application User Model ID 

Modern desktop applications are not always started with an executable file. Example of such apps are all applications from the Windows store, UWP or Maui-based apps. To enable this type of automation Test Studio Desktop tests support configuring a test using the <a href="https://docs.microsoft.com/en-us/windows/win32/shell/appids" target="_blank">Application User Model ID</a>. 

![Configure Application user model ID](/img/automated-tests/desktop-testing/desktop-test/fig6.png)

>__Tip__
><br>
><br>
> __Not sure what is the Applications ID for the tested app?__ Follow <a href="/automated-tests/desktop-testing/desktop-app-user-model-id" target="_blank">few simple steps to find the User Model Id</a> and use it in the Test Studio desktop test configuration. 

## Do Not Launch Desktop Application

This option lets you prevent the automatic start of an application on test startup. If you select it __use the steps to launch an application and connect the Test Studio process__ to it:

- <a href="/features/custom-steps/desktop-common/launch-app-step" target="_blank">Launch application step</a> 
- <a href="/features/custom-steps/desktop-common/connect-to-app" target="_blank">Connect to application step</a>

![Do not launch default app](/img/automated-tests/desktop-testing/desktop-test/fig7.png)

>__Tip__
><br>
><br>
> __Initiate the recording session__ using the <a href="/automated-tests/test-execution/partial-test-execution#run-to-here" target="_blank">partial test run option Run->To Here</a>. 

## Finish Desktop Test Configuration

Once you choose the path to the desktop application executable file, you can __confirm the configuration__ by pressing the __OK__ button. Then, use the <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">__Record__ button</a> to launch the specified app in Test Studio recording mode.

> **Tip**
> <br>
> <br>
> In any case, when you need to change the applied settings, hit the __Configure__ button to access the wizard again.

## See Also:

* <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">Desktop Test Recording Video Tutorial</a>.
