---
title:  Create and Record WPF Test
page_title: Create and Record a WPF Test in Visual Studio Plugin
description: "Create and Record a Test Studio WPF Test in the Visual Studio plugin."
position: 2
---
# Create and Record a WPF Test (VS plugin) 

The feature of Test Studio to record tests by capturing your actions against the tested application is also available in the context of the Visual Studio project.

In this article you can find how to add and record a new WPF test in the Visual Studio plugin project for Test Studio.

## Create a WPF Test

Click with the right mouse button on the project name in __Solution Explorer__, select the __Add...__ option and choose the __Test Studio WPF Test...__ option.

![New WPF test][3]

The chosen item is selected in the list of items and you can enter name for the test. Then click the __Add__ button to insert it in the project.

![Add][4]

To open the test, double click on its name in the Solution Explorer. The WPF test requires the path to the tested application to be configured before you can start recording. Click the __Configure WPF Application__ button in the toolbar to open the window with the WPF test settings.

![Configure WPF app button][5]

The __Configure WPF Application Path__ window appears and you can insert the necessary information:

* <a href="/automated-tests/wpf/wpf-test#choose-the-application-to-automate" target="_blank">Choose the WPF application to automate</a>
* <a href="/automated-tests/wpf/wpf-test#set-default-wpf-application-path" target="_blank">Set default WPF Application path</a>
* <a href="/automated-tests/wpf/wpf-test#record-application-window-state" target="_blank">Record application Window State</a>

Confirm the applied changes with __OK__ button.

![Confirm configuration][6]

## Record Steps in a WPF Test

The __Record__ button is in the test toolbar when a test is opened in the project. Click the button to initiate a recording session.

![Record button in the test toolbar](/img/general-information/create-test-vsplugin/web-test/record-button.png)

Click the __Record__ button to launch the application in recording mode. Once the app is completely loaded, the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Test Studio Recorder Toolbar__</a> gets attached to this instance and you can <a href="/automated-tests/recording/overview#wpf-test-recording" target="_blank">add the steps</a> for the automation scenario.

To __stop the recording session__ close the application

## Execute the Recorded Steps

The <a href="/automated-tests/test-execution/quick-execution" target="_blank">__Quick Execution__ options</a> from Test Studio project are also available in the context of the Visual Studio project. The __Execute__ button is in the test toolbar when a test is opened in the project and is enabled when the test has at least one step to execute.

![Execute test](/img/general-information/create-test-vsplugin/web-test/execute-test.png)

If you want to use the Visual Studio Test Explorer to execute the Test Studio tests, check <a href="/automated-tests/vs-plugin/vs-test-explorer" target="_blank">this topic</a>.

[1]: /img/general-information/create-test-vsplugin/wpf-test/fig1.png
[2]: /img/general-information/create-test-vsplugin/wpf-test/fig2.png
[3]: /img/general-information/create-test-vsplugin/wpf-test/fig3.png
[4]: /img/general-information/create-test-vsplugin/wpf-test/fig4.png
[5]: /img/general-information/create-test-vsplugin/wpf-test/fig5.png
[6]: /img/general-information/create-test-vsplugin/wpf-test/fig6.png
[7]: /img/general-information/create-test-vsplugin/wpf-test/fig7.png
[11]: /img/general-information/create-test-vsplugin/wpf-test/fig11.png
[12]: /img/general-information/create-test-vsplugin/wpf-test/fig12.png