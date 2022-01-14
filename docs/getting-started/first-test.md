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

For your first test in this project add a new **Web** test.

1. Go to the *Project* ribbon and click on the **Add Web Test** button.

    ![Add new test Project Ribbon](/img/getting-started/first-project/fig02.png)

2. This automatically adds a web test in the __Project Explorer__ and the test item is in edit mode, which allows you to enter its meaningful name.

    ![Choose name for the new test](/img/getting-started/first-project/fig03.png)

3. Other test types can be selected from the down arrow of the **Add Web Test** button.

    ![Add other test type test Project Ribbon](/img/getting-started/first-project/fig02a.png)

 Use the links below to find more information on all test types you can add in a Test Studio Web&Desktop project:

*	<a href="/general-information/test-recording/overview" target="_blank">**Web Test**</a>
*	<a href="/features/testing-types/wpf-test" target="_blank">**WPF Test**</a>
*	<a href="/features/testing-types/responsive-test" target="_blank">**Responsive Web Test**</a>
*	<a href="/features/testing-types/load-testing/Overview" target="_blank">**Load Test**</a>
*	<a href="/features/testing-types/performance-testing/overview" target="_blank">**Performance Test**</a>
*	<a href="/features/testing-types/manual-testing/overview" target="_blank">**Manual Test**</a>

> __Tip__
><br>
><br>
> When you start working in the project, you will receive tips and tricks with useful information and links to the documentation. These are based on your actions and you can access the list of <a href="/general-information/start-a-project/in-product-tips-tricks" target="_blank">__Tips and Tricks__</a> at any time from the top right corner of Test Studio.

## Start a Recording Session

Test Studio allows you to easily record the steps of an automated scenario with its click-and-record functionality. The below steps describes how to trigger a recording session and start recording the steps of your test scenario.

1. Open the newly created test with a double-click on it in the __Project Explorer__. In the opened web test, you can click the ***Record*** button in the *Tests* ribbon or press **CTRL+R** to trigger the recording session.

    ![Hit the record button](/img/getting-started/first-project/fig04.png)

2. In the *Recording* dialog type the URL you want to navigate to, select Internet Explorer (or any of the other browsers supported for recording) and press Enter or click the ***Record*** button. You can choose a URL from your recently used URLs.

    ![Choose browser](/img/getting-started/first-project/fig05.png)

    > **Note**
    ><br>
    ><br>
    > Selecting the recording browser will be skipped, if you have already set a preferred browser from the <a href="/general-information/test-execution/quick-execution#preferred-browser" target="_blank">Test ribbon</a>.

3. Once the selected browser navigates to the desired page, the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> gets attached to it. A navigate step is recorded in the *Steps* pane and you can continue recording the next actions as per the required scenario.

    ![Attached recorder](/img/getting-started/first-project/fig06.png)

    > __Important__ 
    ><br>
    ><br>
    > While recording a test, **do not start another instance of the same browser** until the recording is finished!

4. Lets navigate to the [Test Studio documentation](https://docs.telerik.com/teststudio/) from the Telerik page. Click on **DOCS & SUPPORT** button, click on **Test Studio** link and on the next page click on the **Documentation** link. All of those actions are added as steps in the test.

    ![Step pane](/img/getting-started/first-project/fig07.png)

5. To exit the recording session, close the browser with the attached Recording toolbar.

## Compact Recording Toolbar

Following the above steps, you noticed that starting the recording session attached the __Test Studio Compact Recording Toolbar__ to the browser selected for test recording. Let's check what options provides the __Compact Recording Toolbar__.

![Recorder attached to the browser](/img/general-information/test-recording/overview/fig5.png)

The <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Compact Recording Toolbar__</a> is a useful tool, which allows you to extend the recording experience and add specific steps in between recording actions against the application.

![Recording Toolbar](/img/getting-started/first-project/compact-recording-toolbar.png)

1. __Highlight Element__ - one of the most useful features is the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Hover Over Highlighting and the menu</a> with Quick steps to add.
2. __Recording State__ - there is a *Pause* button in case you need to perform any actions against the application, but don't need to record these.
3. __Advanced Recording Tools__ - open the Advanced Recording Tools window to explore the DOM tree of the application and add more steps and verifications.
4. __Rotate Compact Recording Toolbar__ - change the orientation of the Compact Recording Toolbar between vertical and horizontal. You can move it anywhere in the browser/WPF application.
5. __Link to Documentation__ - follow the link to our documentation specifically for the recording process.

<br><br>
<br><br>
<div><a href="/getting-started/first-project">Back to <strong>Launch Test Studio</strong></a><a style="float:right" href="/getting-started/first-execution">Go to <strong>Execute Your First Test</strong></a></div>
