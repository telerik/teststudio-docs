---
title: Record Tests in Test Studio
page_title: Record Tests in Test Studio
description: "A step by step guide on how you can create and record your first test in Test Studio project. Create a test in Test Studio Project. Start automating with Test Studio."
position: 2
---
# Create Your First Test

Once you have successfully <a href="/getting-started/first-project" target="_blank">created a project in Test Studio</a>, you can start with recording the automation tests against the application under test. In this article you can find useful hints on the below topics.

1. [Add a Test to the Project](#add-a-test-to-the-project)
2. [Start a Recording Session](#start-a-recording-session)
3. [Recording Toolbar](#recording-toolbar)

<br><br>
<div><a href="/getting-started/first-project">Back to <strong>Launch Test Studio</strong></a><a style="float:right" href="/getting-started/first-execution">Go to <strong>Execute Your First Test</strong></a></div>

<br>

> __Tip__
><br>
><br>
> Check this <a href="https://www.telerik.com/blogs/test-studio-step-by-step-creating-tests">step-by-step tutorial blog post</a> on how to create your first test.

## Add a Test to the Project

Let's go ahead and add a new __Web__ test in the test project.

1. Go to the *Project* ribbon in the project and click on the __New__ button. This button consists of two areas - the upper one adds a web test by default, the lower one opens a dropdown and lets you choose the type of test to add (skip to step 3. in this tutorial). Use the upper area of the button to add your first web test for this project.

    ![Add new web test button in Project Ribbon](/img/getting-started/first-project/fig02.png)

2. This brings up a popup window and allows you to enter a name for the test. Or, you can leave it with the default suggested name and rename it later from the <a href="/features/project-explorer/overview#test-file-context-menu-options">*Project Explorer Context Menu*</a>. Press the __Ok__ button to confirm adding the new test - it appears in the  __Project Explorer__ and is opened on focus in the test area.

    ![Choose name for the new test](/img/getting-started/first-project/add-web-test.gif)

3. To add a test from any of the other test types, click the down arrow area of the __New__ button in the *Project* ribbon and select the desired one from the dropdown list. You can change the default test name in a similar popup window and confirm the selection by pressing the __Ok__ button. The test appears in the __Project Explorer__ and is opened on focus in the test area.

    ![Add other test type test Project Ribbon](/img/getting-started/first-project/fig02a.png)

You can use the links below to find out more detailed information on all test types you can add in a Test Studio Web&Desktop project:

* <a href="/general-information/test-recording/overview" target="_blank">__Web Test__</a>
* <a href="/features/testing-types/wpf-test" target="_blank">__WPF Test__</a>
* <a href="/features/testing-types/responsive-test" target="_blank">__Responsive Web Test__</a>
* <a href="/automated-tests/desktop-testing/desktop-test" target="_blank">__Desktop Test__</a>
* <a href="/features/testing-types/load-testing/Overview" target="_blank">__Load Test__</a>
* <a href="/features/testing-types/performance-testing/overview" target="_blank">__Performance Test__</a>
* <a href="/features/testing-types/manual-testing/overview" target="_blank">__Manual Test__</a>

> __Tip__
><br>
><br>
> When you start working in the project, you get tips and tricks with useful information and links to the documentation. These are based on your actions and you can access the list of <a href="/general-information/start-a-project/in-product-tips-tricks" target="_blank">__Tips and Tricks__</a> at any time from the top right corner of Test Studio.

## Start a Recording Session

The click-and-record functionality in Test Studio is designed to record the user's actions in web and WPF apps and to represent these as steps in an automated test. Follow the below instructions and find out how to start a recording session and generate the steps of your test scenario.

1. You can continue in the sample project you just created. Select the test you added in the __Project Explorer__ and double click on it - the focus is set in the empty test area and the tools ribbon is switched to *Tests*. You can trigger the recording session either by clicking on the __Record__ button in the ribbon, or the *camera icon* in the test area.

    ![Click the record button](/img/getting-started/first-project/fig04.png)

    > __Tip__
    ><br>
    ><br>
    > You can use the keyboard shortcut __Ctrl+R__ to start the recording session in the context of the active test.

2. Starting the __recording session from a web test__ triggers the *Recording* dialog. You need to type the URL to navigate to (you can pick a URL from the list of recently used URLs) and select any of the supported for recording browsers. Click the *__Record__* button or press the *Enter* key to start the recording.

    ![Choose browser](/img/getting-started/first-project/fig05.png)

    > __Tip__
    ><br>
    ><br>
    > If you have already <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set a preferred browser</a>, the recording always starts with this type of browser.

3. The selected browser starts and navigates to the selected page and once the page is entirely loaded the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Test Studio Compact Recording Toolbar__</a> gets attached to the browser instance. A _Navigate_ step is recorded in the test for this initial action and you can continue acting upon the page as usually. Test Studio records all user actions towards the page and represents these as steps in the test.

    ![Attached recorder web app](/img/getting-started/first-project/fig06.png)

    > __Important__
    ><br>
    ><br>
    > While recording a web test, __do not start another instance of the same browser__ until the current recording session is finished!

4. Starting the __recording session from a WPF test__ for first time triggers the *Configure WPF Application Path* dialog. You need to <a href="/automated-tests/wpf/wpf-test#choose-the-application-to-automate" target="_blank">specify the application to be used</a> for creating the tests, then click the __OK__ button to trigger the recording. Once the test is configured with an application, the __Record__ button starts that one automatically in recording mode.

    ![Configure WPF](/img/getting-started/first-project/fig05a.png)

5. Starting the __recording session from a desktop test__ for first time triggers the *Configure Desktop Application Path* dialog. You need to <a href="/automated-tests/desktop-testing/desktop-test#choose-the-desktop-application-to-automate" target="_blank">specify the application to be used</a> for creating the tests, then click the __OK__ button to trigger the recording. Once the test is configured with an application, the __Record__ button starts that one automatically in recording mode.

    ![Configure desktop app](/img/getting-started/first-project/fig05b.png)

6. The configured application - WPF or Desktop - starts and once it is loaded entirely the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Test Studio Compact Recording Toolbar__</a> gets attached to it.

    <table id="no-table">
    <tr>
    <td> ![Attached recorder WPF app][1] <br><br>Recording WPF Application</td>
    <td> ![Attached recorder desktop app][2] <br><br>Recording Desktop Application</td>
    <tr>
    <table>

7. To __stop the recording session__, close the application instance (browser, desktop or WPF) with the attached Recording Toolbar.

## Compact Recording Toolbar

Following the above steps, you noticed that starting the recording session attached the __Test Studio Compact Recording Toolbar__ to the browser selected for test recording. Let's check what options provides the __Compact Recording Toolbar__.

![Recorder attached to the browser](/img/general-information/test-recording/overview/fig5.png)

The <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Compact Recording Toolbar__</a> is a powerful tool, which enables additional useful features to  enhance the recording experience. You can pause or continue the recording of actions, enable or disable the elements highlighting to use the Quick Step menu, open the Advanced Recording Tools to explore the DOM in further details, etc. Check the list below for details of the options in the toolbar.

![Recording Toolbar](/img/getting-started/first-project/compact-recording-toolbar.png)

1. __Highlight Element__ - enables or disables the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Element Highlighting</a> and the Quick Steps menu.
2. __Recording State__ - there is a *Pause* button in case you need to perform any actions against the application, but don't need to record these. When the recording is paused, the button is switched to a *Resume* mode to trigger the recording again.
3. __Advanced Recording Tools__ - open the Advanced Recording Tools window to explore <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">the DOM tree of the application, add <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">element specific steps</a> or include <a href="/features/recorder/advanced-recording-tools/browser-control" target="_blank">browser specific actions</a> or <a href="/features/recorder/advanced-recording-tools/common-steps" target="_blank">common steps</a> between the recorded steps.
4. __Rotate Compact Recording Toolbar__ - change the orientation of the Compact Recording Toolbar between vertical and horizontal. You can move it anywhere in the browser/WPF application.
5. __Link to Documentation__ - follow the link to our documentation describing the recording process in details.

<br><br>
<br><br>
<div><a href="/getting-started/first-project">Back to <strong>Launch Test Studio</strong></a><a style="float:right" href="/getting-started/first-execution">Go to <strong>Execute Your First Test</strong></a></div>

## See Also:

* <a href="/features/project-settings/browsers" target="_blank">Calibrate Browsers</a>
* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-creating-tests" target="_blank">Step-by-Step: Creating Tests</a>
* <a href="https://www.telerik.com/videos/teststudio/test-recorder-video-tutorial-test-studio" target="_blank">Web Test Recorder Video Tutorial</a>
* <a href="https://www.telerik.com/videos/teststudio/test-recorder-for-wpf-video-tutorial-test-studio" target="_blank">WPF Test Recorder Video Tutorial</a>.

[1]: /img/getting-started/first-project/fig06a.png
[2]: /img/getting-started/first-project/fig06b.png