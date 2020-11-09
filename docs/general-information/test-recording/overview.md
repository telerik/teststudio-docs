---
title: Test Recording Overview
page_title: Test Recording Overview
description: "Test Studio test Recording codeless. Record a test in Test Studio without writing code. Launch new browser to record a test. Can I start recording from certain point in my application. Can I attach Test Studio to a running browser or application. Codeless test automation with Test Studio."
position: 0
---
# Test Recording #

The **Test Recording** is one of the main features of Test Studio. It allows you to capture your actions automatically without writing any code. You can also add the necessary verification steps to help you automate the test scenario. 

## Start Recording ##

You can start recording your tests, by clicking the Record button. This will open a new instance of the browser or WPF application with the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> attached to it. When you want to stop the recording session, simply close the browser or WPF application.

1.&nbsp;  Double click the test to open it. Click the **Record** button in the **Tests** tab or press **CTRL+R**.

<table id=no-table>
	<tr>
		<td>![Test Studio][1] <br><br>**Standalone version**</td>
		<td>![VS][2] <br><br>**VS plugin**</td>
	</tr>
<table>

2.&nbsp; In the next dialog type the URL you want to navigate to, select the recording browser and press Enter or the *Record* button in that window. You can choose a URL from your recent URLs.

> **Note**
> <br>
> Selecting the recording browser will be skipped if you have already set a preferred browser from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Test ribbon</a>.

![Choose browser][3]

If you enable **Save my choice for the future** or you have set a preferred browser from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Test ribbon</a> the **Record** button in the Test Studio project will display the icon for the selected default browser.

![Choose preferred browser][4]

3.&nbsp; Once the selected browser navigates to the desired page or the WPF application is started, the recorder gets attached to it. A navigate step is recorded in the Steps pane and you can continue recording the next actions as per the required scenario.

![Attached recorder][5]

> **Note**
> <br>
> Once a recording session is started **do not start another instance of the same browser** until the session is finished!

## Compact Recorder ##

Once you have started a recording session, you will see the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> attached to the browser or WPF application. You can move it on the screen freely  You can use the **Compact Recording Toolbar** to explore the application under test's structure, add actions, verifications and common steps for your test scenario.

![Compact recording toolbar][6]

* Enable/Disable hover over highlighting to annotate the elements that you hover over. You will see the <a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Elements Menu</a> pop-up with multiple options.
* Pause/Resume recording button allows you to pause or resume the recording. When it is paused, your actions against the application under test will not be added to the test.
* Show/Hide the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">Advanced Recording Tools</a>, where you can explore the DOM tree and add more types of steps against a specific element.
* Switch the orientation of the **Compact Recording Toolbar** between vertical and horizontal.

## See also ##

* <a href="/features/project-settings/browsers" target="_blank">Calibrate Browsers</a>
* <a href="/features/recorder/test-recording" target="_blank">Recording Features</a>

[1]: /img/general-information/test-recording/overview/fig1.png
[2]: /img/general-information/test-recording/overview/fig2.png
[3]: /img/general-information/test-recording/overview/fig3.png
[4]: /img/general-information/test-recording/overview/fig4.png
[5]: /img/general-information/test-recording/overview/fig5.png
[6]: /img/general-information/test-recording/overview/fig6.png
