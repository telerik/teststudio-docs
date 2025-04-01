---
title: Create and Record Web Test
page_title: Create and Record a Web Test in Visual Studio Plugin
description: "Create and Record a Test Studio Web Test in the Visual Studio plugin."
position: 1
---
# Create and Record a Web Test (VS plugin)

The feature of Test Studio to record tests by capturing your actions against the tested application is also available in the context of the Visual Studio project.

In this article you can find how to add and record a new web test in the Visual Studio plugin project for Test Studio.

## Create a Web Test

Each newly created Test Studio project in Visual Studio contains one empty web test. Double click the test file (WebTest1.tstest) in the __Solution Explorer__ to open it. Right click on it to choose the option to rename it.

![Open web test](/img/general-information/create-test-vsplugin/web-test/open-test.png)

When you need to add new tests in the project, click with the right mouse button on the project name in __Solution Explorer__, select the __Add...__ option and choose between __Test Studio Web Test...__ or __Test Studio WPF Test...__.

![Add new test](/img/general-information/create-test-vsplugin/web-test/add-new-test.png)

The chosen item is selected in the list of items and you can enter name for the test. Then click the __Add__ button to insert it in the project. To open the test, double click on its name in the Solution Explorer.

![Open new test](/img/general-information/create-test-vsplugin/web-test/open-new-test.png)

## Record Steps in a Web Test

The __Record__ button is in the test toolbar when a test is opened in the project. Click the button to initiate a recording session.

![Record button in the test toolbar](/img/general-information/create-test-vsplugin/web-test/record-button.png)

The __Recording__ dialog pops up and you can enter the URL of the page you test and select which browser to use for this recording session. In the __Recent URLs__ section you can find and  select the URls used in the latest recording sessions.

![Select url and browser](/img/general-information/create-test-vsplugin/web-test/enter-url.png)

Click the __Record__ button to launch the browser in recording mode. The selected browser starts and navigates to the listed URL. Once the page is completely loaded, the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Test Studio Recorder Toolbar__</a> gets attached to the browser instance and you can <a href="/automated-tests/recording/overview#how-to-add-steps-in-the-test" target="_blank">add the steps</a> for the automation scenario.

![Browser with attached recorder][6]

To __stop the recording session__ close the browser.

## Execute the Recorded Steps

The <a href="/automated-tests/test-execution/quick-execution" target="_blank">__Quick Execution__ options</a> from Test Studio project are also available in the context of the Visual Studio project. The __Execute__ button is in the test toolbar when a test is opened in the project and is enabled when the test has at least one step to execute.

![Execute test](/img/general-information/create-test-vsplugin/web-test/execute-test.png)

If you want to use the Visual Studio Test Explorer to execute the Test Studio tests, check <a href="/automated-tests/vs-plugin/vs-test-explorer" target="_blank">this topic</a>.






[6]: /img/general-information/create-test-vsplugin/web-test/fig6.png
