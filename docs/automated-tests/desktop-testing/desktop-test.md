---
title: Desktop Tests
page_title: Configure Desktop Test
description: "Testing a desktop app with Test Studio. Configure Dekstop Test (Standalone) in Test Studio for automating dekstop application. Create a Dekstop test in Test Studio and record an automated scenario for desktop app. "
position: 1
---
# Dekstop Tests in Test Studio (Beta)

Test Studio recording feature supports various desktop applications. To be able to initiate recording session against specific application, you need to list its executable in the desktop test.

> **Disclaimer**
> <br>
> <br>
> The Desktop test feature is officially __released with Test Studio R2 2022 (v.2022.2.727) in Beta__ stage. It supports basic recording features including highlighting and partial test execution, elements repository represented in the Elements Explorer and editing the recorded elements.

This article guides you through the desktop test configuration process.

- [Configure Desktop Test to Record Specific Application](#configure-desktop-test-to-record-specific-application)
- [Choose the Desktop Application to Automate](#choose-the-desktop-application-to-automate)
- [Finish Desktop Test Configuration](#finish-desktop-test-configuration)

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">this video tutorial for recording an end-to-end Desktop test scenario</a>.

## Configure Desktop Test to Record Specific Application

The __configuration of the desktop test requires an executable file of a valid desktop app to be specified__ and, thus, used for recording and execution. Open a Desktop test in Test Studio and find the __Configure__ button in the __Test__ tools ribbon. Click the __Configure__ button to open the __Desktop App Config Wizard__.

![Configure button](/img/automated-tests/desktop-testing/desktop-test/fig1.png)

> **Tip**
> <br>
> <br>
> If you attempt to initiate a recording session in a desktop test, before it is configured, the __Desktop Config Wizard__ pops up and lets you choose the application to automate.

## Choose the Desktop Application to Automate

Test Studio provides two options to define the application to automate - you can specify an executable file for this test, or use a default path set on project level.

![Config Desktop app wizard](/img/automated-tests/desktop-testing/desktop-test/fig2.png)

### Configure Specific App in Desktop Test

Choose the __Browse__ button to open File Explorer and browse to the folder where the executable file is and select it.

![Specify path to Desktop app](/img/automated-tests/desktop-testing/desktop-test/fig3.png)

The __Desktop Application Path__ field also allows you to use environment tokens (i.e. _%Program Files%\MyApp\App.exe_). In any case the __Full Path__ field displays the full path to the executable file.

![Full application path](/img/automated-tests/desktop-testing/desktop-test/fig4.png)

### Use Default Desktop Application Path

The automation process requires multiple tests to be created for a single application. In such case configuring each created test will be a tedious task. Therefore Test Studio allows you to __set a default desktop app path on project level__ and use this for all desktop tests. The option is available in <a href="/features/project-settings/general" target="_blank">Project Settings -> General</a> and once a __Default Desktop App is set__ each new Desktop test in the project is created directly configured to use it.

![Use default path](/img/automated-tests/desktop-testing/desktop-test/fig5.png)

## Finish Desktop Test Configuration

Once you choose the path to the desktop application executable file, you can __confirm the configuration__ by pressing the __OK__ button. Then, use the <a href="/automated-tests/recording/overview#start-a-recording-session" target="_blank">__Record__ button</a> to launch the specified app in Test Studio recording mode.

> **Tip**
> <br>
> <br>
> In any case, when you need to change the applied settings, hit the __Configure__ button to access the wizard again.

## See Also:

* <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">Desktop Test Recording Video Tutorial</a>.
