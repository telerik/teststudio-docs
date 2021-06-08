---
title: How to Record Test
page_title: How to Record Test
description: "Test Studio allows you to record tests against an application without writing code. You can attach Test Studio to a running browser or application."
position: 0"
---
# How to Record Test

The **Test Recording** feature in Test Studio automatically captures your actions against the tested application. While recording, you can add various verification steps that test the page.

**Test Recording** provides built-in translators for all Telerik components. These translators allow you to automate a variety of actions and verifications for the controls. None of **Test Recording** features requires you to write code.

This article guides you through the recording process for web and WPF tests and how to get the most out of them.

1. [How to Start a Recording Session](#start-a-recording-session)
1. [How to Add Steps in the Test](#how-to-add-steps-in-the-test)
1. [Example of a Web Test Recording](#web-test-recording)
1. [Example of a WPF Test Recording](#wpf-test-recording)
1. [Stop the Recording Session](#stop-the-recording-session)
1. [Attach the Recorder to a Running Application](#attach-the-recorder-to-a-running-application-applicable-for-ie-or-wpf-only)
1. [What is the Compact Recorder](#what-is-the-compact-recorder)

## Start a Recording Session

When you open a web or WPF test is and it becomes active in the current Test Studio project, the toolbar ribbon switches to the __Tests__ tab. This tab provides options that control the recording and execution of a test in Test Studio.

![Test Ribbon Toolbar][2]

You can start a recording session by clicking __Record__.

![Test Studio][1]

> **Tip**
> <br>
> <br>
> You can start the recording session with the **Ctrl+R** keyboard shortcut or by using the __Record__ context menu option in the __Project Explorer__.

## Add Steps to a Test

You can use the following approaches to add steps to a test:

* The <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Compact Recording Toolbar__</a> &mdash;detects any actions performed against the tested application and adds them as steps. Some of these actions are: clicking on page elements, entering text, triggering of dialogs, handling of dialogs, navigating to a page, opening a pop-up window and performing actions in it, etc.

* The <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Quick Highlighting Menu__</a>&mdash;allows you to add predefined steps.

* The <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">__Advanced Recording Tools__</a>&mdash;allow you to build complex steps.

* The <a href="/features/custom-steps/overview" target="_blank">__Step Builder pane__</a> allows you to add steps that are not related to a specific application or application element, for example, adding a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a>, <a href="/features/custom-steps/test-as-step" target="_blank">a test as a step</a>, a comment, <a href="/features/logical-steps/if-else" target="_blank">an `if...else` statement</a>, <a href="/features/custom-steps/capture" target="_blank">refreshing the browser</a>, etc.

### Record Web Tests

To start a recording session for a web test, enter the URL of the target page and the desired browser in the __Recording__ dialog.

![Enter URL, Choose browser][3]

> **Tip**
> <br>
> <br>
> If you plan to use a specific browser for the test automation project, select the browser, and then select __Save my choice for the future__. This will <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set the browser as preferred</a> for the current project and the **Select Browser** prompt won't appear again.

To launch the selected browser and navigate to the desired URL, click __Record__ in the __Recording__ dialog. This will start a new instance of the browser and launch the Test Studio extension, if available. Next, the target page loads and the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> appears on top of the browser.

![Attached recorder][5]

To verify that a **Navigate to** step was recorded, switch back to the project. The first step in the list points to the URL that you used to start the web test.

![Recorded navigate step][5a]

> **Note**
> <br>
> <br>
> Once a recording session starts, do not start another instance of the same browser until the session finishes!

### Record WPF Tests

To start the test automation for a WPF application, click __Configure__ and then point to the application's executable file. This is called <a href="/automated-tests/wpf/wpf-test" target="_blank">WPF test configuration</a>.

![Configure WPF Test button][10]

After configuring the WPF test, you can begin recording the automation scenario against the WPF application. To start a recording session, use the __Record__ button. This launches the defined executable file and attaches the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> on top of the app.

![Record WPF Test][11]

> **Tip**
> <br>
> <br>
> To start the recording session for WPF tests, you can also use the **Ctrl+R** keyboard shortcut or the __Record__ context menu option in the __Project Explorer__.

The Test Studio UI remains in the background and records all your actions against the tested application.

![Recorded steps in WPF Test][12]

## Stop the Recording Session

To terminate an active recording session, close the automated browser or WPF application - this is how all processes and communication channels between the app and Test Studio get dismissed.

## Attach the Recorder to a Running Application (Applicable for IE or WPF Only)

You can attach a recorder to an already running application. To start the recording session, use the dropdown under the __Record__ button. In the list, you can see all compatible processes where you can attach the Test Studio recorder. Select one and wait for the __Compact Recorder__ to attach to the application.

<table id=no-table>
	<tr>
		<td>![Attach to running browser][8] <br><br>**Web Test - Internet Explorer only**</td>
		<td>![Attach to running WPF instance][7] <br><br>**WPF Test - connect to running WPF application instance**</td>
	</tr>
<table>

> **Note**
> <br>
> <br>
> Attaching a recording session to an existing process is applicable only to Internet Explorer or WPF applications. If you need to cover a similar recording scenario for other browsers (Chrome, Edge Chromium, Firefox), use the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>.

## What is the Compact Recorder

The <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> gets attached to the automated application during every recording session. It is the connection between the application under test and Test Studio.

The toolbar's size is minimal and you can change its position at any time. Through the __Compact Recording Toolbar__, you get access to various recording actions, for example:

* Highlight and add elements to the test project.
* Explore the application under the test's structure and its elements.
* Add actions, verifications, and common steps for your test scenario.

![Compact recording toolbar][6]

The __Compact Recording Toolbar__ provides quick access to the following buttons:

* __Enable/Disable hover over highlighting__&mdash;used to highlight the elements that you hover over in order to access the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Elements Menu</a> pop-up that provides multiple options for the specific element.
* __Pause/Resume recording__&mdash;allows you to pause or resume the recording. When paused, your actions against the application under test will not be added to the test.
* __Show/Hide the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">Advanced Recording Tools</a>__&mdash;in the __Advanced Tools__ you have access to the application's DOM tree and various types of steps for the selected element.
* __Switch the orientation of the **Compact Recording Toolbar** between vertical and horizontal__&mdash;this is an additional feature to increase your productivity and allow you to place the toolbar anywhere outside of the working area.

## See also ##

* <a href="/features/project-settings/browsers" target="_blank">Calibrate Browsers</a>
* <a href="/automated-tests/wpf/wpf-test" target="_blank">Configure WPF Application</a>


[1]: /img/automated-tests/recording/overview/fig1.png
[2]: /img/automated-tests/recording/overview/fig2.png
[3]: /img/automated-tests/recording/overview/fig3.png
[4]: /img/automated-tests/recording/overview/fig4.png
[5]: /img/automated-tests/recording/overview/fig5.png
[5a]: /img/automated-tests/recording/overview/fig5a.png
[6]: /img/automated-tests/recording/overview/fig6.png
[10]: /img/automated-tests/recording/overview/fig10.png
[11]: /img/automated-tests/recording/overview/fig11.png
[12]: /img/automated-tests/recording/overview/fig12.png
[8]: /img/features/recorder/test-recorder/fig6.png
[7]: /img/features/recorder/test-recorder/fig7.png
