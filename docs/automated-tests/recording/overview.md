---
title: How to Record Test
page_title: How to Record Test
description: "Test Studio test Recording codeless. Record a test in Test Studio without writing code. Launch new browser to record a test. Can I start recording from certain point in my application. Can I attach Test Studio to a running browser or application. Codeless test automation with Test Studio."
position: 0
---
# How to Record Test

**Test Recording** is one of the leading Test Studio features, which automatically captures your actions against the application under test. While recording, you can also add various verification steps to ensure the page's state. A key benefit to mention are the built-in translators for all Telerik components, which allow you to automate specific actions and verifications for the controls. And all these are part of the recording flow without the need for a single line of code.

This article will guide you through the recording process for web and WPF tests and how to get the most out of them.

1. [How to Start a Recording Session](#start-a-recording-session)
1. [How to Add Steps in the Test](#how-to-add-steps-in-the-test)
1. [Example of a Web Test Recording](#web-test-recording)
1. [Example of a WPF Test Recording](#wpf-test-recording)
1. [Stop the Recording Session](#stop-the-recording-session)
1. [Attach the Recorder to a Running Application](#attach-the-recorder-to-a-running-application-applicable-for-ie-or-wpf-only)
1. [What is the Compact Recorder](#what-is-the-compact-recorder)

## Start a Recording Session

When a web or WPF test is opened and active in the Test Studio project, the toolbar ribbon is switched to the __Tests__ tab. It provides options to control the recording and execution process of a test in Test Studio.

![Test Ribbon Toolbar][2]

You can start a recording session by clicking __Record__.

![Test Studio][1]

> **Tip**
> <br>
> <br>
> You can start the recording session with the **Ctrl+R** keyboard shortcut or by using the __Record__ context menu option in the __Project Explorer__.

## Add Steps in the Test

* You can use the **Compact Recording Toolbar** to add steps. The Test Studio <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> __detects any actions performed against the application under test__ - click on any element, enter text, trigger a dialog and handle it, navigate to a page, open a pop-up window and perform actions in it, etc.

* Apart from all direct interaction, which can be sent towards the tested application, you can __add different types of steps__ from the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Quick Highlighting Menu__</a>, or __build more complex steps__ in the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">__Advanced Recording Tools__</a>.

* To add steps, which are not related to a specific application or element from it, you can also __add Common Steps from the__ <a href="/features/custom-steps/overview" target="_blank">__Step Builder pane__</a> - like adding a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a>, or a <a href="/features/custom-steps/test-as-step" target="_blank">test as step</a>, comment, or <a href="/features/custom-steps/capture" target="_blank">refreshing the browser</a>, <a href="/features/logical-steps/if-else" target="_blank">if...else statement</a>, etc.

### Record Web Tests

When starting a recording session in the context of a web test, you need to __enter the URL__ of the page to automate and __choose a browser__ to load the application in. The __Recording__ dialog, which appears, allows you to define these parameters.

![Enter URL, Choose browser][3]

> **Tip**
> <br>
> <br>
> If you plan to use a specific browser for the automation project, you can select that browser, and then select the checkbox __Save my choice for the future__  - this will <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set the browser as preferred</a> for this project and you won't be prompted to select a browser for recording.

To launch the selected browser and navigate to the listed URL, click the __Record__ button in the __Recording__ dialog. This will start a new instance of the browser and launch the Test Studio extension, if available. Then the target page will be loaded and the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> will appear on top of the browser.

![Attached recorder][5]

The Test Studio UI remains in the background of the browser, but once the page is loaded and the __Compact Recorder__ is attached, you can switch back to the project and check that a _Navigate_ step is recorded using the same URL as defined when starting the recording session.

![Recorded navigate step][5a]

> **Note**
> <br>
> <br>
> Once a recording session is started, **do not start another instance of the same browser** until the session is finished!

### Record WPF Tests

The WPF application is a desktop app and requires a different test recording automation process - you need to __define which is the application to test and where is its executable file__ - this is called <a href="/automated-tests/wpf/wpf-test" target="_blank">configuration of the WPF test</a>.

When you open a WPF test in the automation project, you see a __Configure__ button instead of the browser and web application control options in the toolbar ribbon. The __Configure__ button opens the __WPF Test Config__ dialog.

![Configure WPF Test button][10]

When the application details are configured, you can start recording the automation scenario against the WPF application. To start a recording session, use the __Record__ button. This launches the executable file listed in the _configuration_ process and attaches the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> on top of the app.

![Record WPF Test][11]

> **Tip**
> <br>
> <br>
> You can start the recording session for WPF tests also with the **Ctrl+R** keyboard shortcut or by using the __Record__ context menu option in the __Project Explorer__.

The Test Studio UI remains in the background of the application, but once you initiate any action against the application, this gets recorded in the test.

![Recorded steps in WPF Test][12]

## Stop the Recording Session

To completely terminate an active recording session, __close the automated browser or WPF application__ - this is how all processes and communication channels between the app and Test Studio get dismissed.

## Attach the Recorder to a Running Application (Applicable for IE or WPF Only)

You can attach a recorder to an already running application when it is in certain state, and then continue the recording process.

To trigger a recording session against an already started application, you use the dropdown under the __Record__ button. In the list, you can see all compatible processes, to which the Test Studio recorder can be attached. Select one and wait for the __Compact Recorder__ to attach to the application.

<table id=no-table>
	<tr>
		<td>![Attach to running browser][8] <br><br>**Web Test - Internet Explorer only**</td>
		<td>![Attach to running WPF instance][7] <br><br>**WPF Test - connect to running WPF application instance**</td>
	</tr>
<table>

> **Note**
> <br>
> <br>
> Attaching a recording session to an existing process is __only applicable for Internet Explorer or WPF applications__. If you need to cover a similar recording scenario for the other browsers (Chrome, Edge Chromium, Firefox), you can use the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">__options for partial test execution__</a>.

## What is the Compact Recorder

The  <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> gets attached to the automated application for every recording session, and it can be considered as __the connection between the application under test and Test Studio__.

To ease you in recording the test scenarios, the __toolbar's size is minimal on top of the application window, and you can change its position__ at any time. Through the __Recording Toolbar__, you have access to helpful resources for the recording process - highlight and add elements to the test project, explore the application under the test's structure and its elements, add actions, verifications, and common steps for your test scenario.

![Compact recording toolbar][6]

Below you can find a short description of each toolbar button:

* __Enable/Disable hover over highlighting__ - used to highlight the elements that you hover over in order to access the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Elements Menu</a> pop-up with multiple options for the specific element.
* __Pause/Resume recording button__ - allows you to pause or resume the recording. When paused, your actions against the application under test will not be added to the test.
* __Show/Hide the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">Advanced Recording Tools</a>__ - in the __Advanced Tools__ you have access to the application's DOM tree and various types of steps for the selected element.
* __Switch the orientation of the **Compact Recording Toolbar** between vertical and horizontal__ - this is an additional feature to increase your productivity and allow you to place the toolbar anywhere outside of the working area.

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
