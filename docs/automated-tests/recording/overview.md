---
title: How to Record Test
page_title: Recording Tests in Test Studio
description: "With the visual test recorder in Test Studio you can record codeless tests for web and WPF applications. Check out how to start a recording session for your application and create completely codeless automated tests with Test Studio."
position: 0
---
# Recording Tests in Test Studio

The __Compact Recording Toolbar__ in Test Studio is the key element in recording tests. Once attached to an application it detects how you act upon the app and represent your actions as automated steps in the test. It also gives access to a variety of useful features enabling you for an entirely codeless testing experience.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

This article guides you trough the __recoding workflow for web and WPF tests__ and how you can get the most out of it.

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/test-recorder-video-tutorial-test-studio" target="_blank">this video tutorial for recording an end-to-end web test scenario</a>.

* [How to Start a Recording Session](#start-a-recording-session)
* [Example of a Web Test Recording](#web-test-recording)
* [Example of a WPF Test Recording](#wpf-test-recording)
* [Example of a Desktop Test Recording](#desktop-test-recording)
* [How to Add Steps in the Test](#how-to-add-steps-in-the-test)
* [Stop the Recording Session](#stop-the-recording-session)
* [Attach the Recorder to a Running Application](#attach-the-recorder-to-a-running-application-applicable-for-ie-or-wpf-only)
* [What is the Compact Recorder](#what-is-the-compact-recorder)

## Start a Recording Session

Create a web, desktop or WPF test in the Test Studio project and open it. This changes the tools ribbon to __Tests__ and lets you start a recording session. You can use the __Record__ button from the ribbon, or the _camera icon_ in the opened test pane.

![Test Studio][1]

> **Tip**
> <br>
> <br>
> You can use the keyboard shortcut **Ctrl+R** or the Project Explorer <a href="/features/project-explorer/overview#test-file-context-menu-options" target="_blank">test context menu</a> option __Record__ to start the recording session.

### Web Test Recording

To start a recording session in the context of a web test you need to __enter the URL__ of the page to automate and __choose a browser__ to load the application in. You can define these in the _Recording_ dialog, which appears after clicking the __Record__ button.

![Enter URL, Choose browser][3]

> **Tip**
> <br>
> <br>
> If you plan to __use a specific browser for the automation project__, you can select that browser and enable the checkbox __'Save my choice for the future'__ - this will <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">set the browser as a preferred one</a> for this project and you will no longer be prompted to select a browser for recording and execution.

Hit the __Record__ button in the _Recoding_ dialog to start the recording - a new instance of the browser starts and loads the selected page. Once the page is completely loaded the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> appears on top of the browser.

![Attached recorder][5]

The Test Studio UI remains in the background of the browser and logs the actions as steps in the test - you can switch back to the project to check a _Navigate_ step is recorded with the same URL as defined when starting the recording session.

![Recorded navigate step][5a]

> **Note**
> <br>
> <br>
> While recording a web test, __do not start another instance of the same browser__ until the current recording session is finished!

### WPF Test Recording

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/test-recorder-for-wpf-video-tutorial-test-studio" target="_blank">this video tutorial for recording an end-to-end WPF test scenario</a>.

To start a a recording session in the context of a WPF test you need to define the WPF application to automate. The first time you click the __Record__ button in the WPF test, it triggers the <a href="/automated-tests/wpf/wpf-test" target="_blank">__Configure WPF Application Path__ dialog</a> where you can browse to the executable file of the WPF app to test.

![Configure WPF Test button][10]

Hit the __OK__ button in the __Configure WPF Application Path__ dialog to start the recording session - a new instance of the application starts and loads as it is expected to. Once the application is completely loaded the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> appears on top of the app.

![Record WPF Test][11]

The Test Studio UI remains in the background of the application and logs the actions as steps in the test. You can switch to the Test Studio project at any time and delete or modify the already recorded actions.

![Recorded steps in WPF Test][12]

### Desktop Test Recording

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">this video tutorial for recording an end-to-end desktop test scenario</a>.

To start a recording session in the context of a desktop test you need to define the application to automate. The first time you click the __Record__ button in the desktop test, it triggers the <a href="/automated-tests/desktop-testing/desktop-test#configure-desktop-test-to-record-specific-application" target="_blank">__Configure Desktop Application Path__ dialog</a> where you can browse to the executable file of the app to test.

![Configure desktop app for testing](/img/automated-tests/desktop-testing/desktop-test/fig1.png)

Hit the __OK__ button in the __Configure Desktop Application Path__ dialog to start the recording session - a new instance of the application starts and loads as it is expected to. Once the application is completely loaded the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> appears on top of the app and you can continue <a href="/automated-tests/desktop-testing/recording-specifics-desktop-test" target="_blank">recording the scenario for the desktop app</a>.

![Ready to record desktop app](/img/automated-tests/desktop-testing/recording-specifics/fig2.png)

The Test Studio UI remains in the background of the application and logs the actions as steps in the test.

![Recorded](/img/automated-tests/desktop-testing/recording-specifics/recorded-steps.png)

## How to Add Steps in the Test

* The Test Studio <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> __detects any actions performed against the application under test__ - click on any element, enter text, trigger a dialog and handle it, navigate to a page, open a pop-up window and perform actions in it, etc.

* Apart from all direct interaction, which can be sent towards the tested application, you can __add different type of steps__ from the <a href="/features/recorder/compact-recording-toolbar" target="_blank">__Quick Highlighting Menu__</a>, or __build more complex steps__ in the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">__Advanced Recording Tools__</a>.

* And, finally, when it comes to steps, which are not related to a specific application or element from it, you can also __add Common Steps from the__ <a href="/features/custom-steps/overview" target="_blank">__Step Builder pane__</a> - like adding a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a>, or a <a href="/features/custom-steps/test-as-step" target="_blank">test as step</a>, comment, or <a href="/features/custom-steps/capture" target="_blank">refreshing the browser</a>, <a href="/features/logical-steps/if-else" target="_blank">if...else statement</a>, etc.

> **Tip**
> <br>
> <br>
> Check out this <a href="https://www.youtube.com/watch?v=Klt3fRglAeU&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=3">video tutorial</a> about wait and verification steps in Test Studio.

## Stop the Recording Session

To stop the current recording session __close the automated browser or WPF/desktop application__ - this is how all processes and communication channels between the app and Test Studio gets dismissed.

## Attach the Recorder to a Running Application (Applicable for IE and WPF Only)

The specifics of the recording process allow to __attach a recorder and trigger a recording session to an already running IE browser or WPF application__. To start such recording session you need to use the dropdown under the __Record__ button - in the list you can see all compatible processes, to which Test Studio recorder can be attached. Select one and wait for the __Compact Recorder__ to attach to the application.

<table id=no-table>
	<tr>
		<td>![Attach to running browser][8] <br><br>**Web Test - Internet Explorer only**</td>
		<td>![Attach to running WPF instance][7] <br><br>**WPF Test - connect to running WPF application instance**</td>
	</tr>
<table>

> **Note**
> <br>
> <br>
> Attaching a recording session to an existing process is __only applicable for Internet Explorer or WPF application__. If you need to cover similar recording scenario for the other browsers (Chrome, Edge Chromium, Firefox), you can use the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">__options for partial test execution__</a>.

## What is the Compact Recorder

The  <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> gets attached to the automated application for every recording session and it can be considered as __the connection between the application under test and Test Studio__.

To ease you in recording the test scenarios, the __toolbar's size is minimal on top of the application window and you can change its position__ at any time. Through the _Recording Toolbar_ you have access to helpful resources for the recording process - highlight and add elements to test project, explore the application under test's structure and its elements, add actions, verifications and common steps for your test scenario.

![Compact recording toolbar][6]

Below you can find a short description of each button in the toolbar (in the order these are listed) and reference for further details:

* __Enable/Disable hover over highlighting__ - used to highlight the elements that you hover over in order to access the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Elements Menu</a> pop-up with multiple options for the specific element.
* __Pause/Resume recording button__ - allows you to pause or resume the recording. When it is paused, your actions against the application under test will not be added to the test.
* __Show/Hide the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">Advanced Recording Tools</a>__  in the _Advanced Tools_ you have access to the application's DOM tree and various types of steps for the selected element.
* __Switch the orientation of the **Compact Recording Toolbar** between vertical and horizontal__ - this is additional feature to increase your productivity and allow you place the toolbar anywhere outside of the working area.

## See Also:

* <a href="/features/project-settings/browsers" target="_blank">Calibrate Browsers</a>
* <a href="https://www.telerik.com/blogs/test-studio-step-by-step-creating-tests" target="_blank">Step-by-Step: Creating Tests</a>
* <a href="https://www.telerik.com/videos/teststudio/test-recorder-video-tutorial-test-studio" target="_blank">Web Test Recorder Video Tutorial</a>
* <a href="https://www.telerik.com/videos/teststudio/test-recorder-for-wpf-video-tutorial-test-studio" target="_blank">WPF Test Recorder Video Tutorial</a>.

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
