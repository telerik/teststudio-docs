---
title: Test Recorder
page_title: Test Recorder
description: "Overview of the recording feature in Test Studio. Codeless test step recording. Automate test scenarios without code. Codeless automation."
position: 1
---

# Test Recorder #

The **Test Recorder** is a powerful feature in Test Studio. You can use it to built codeless tests with common actions and verifications or more advanced steps against a specific element in the DOM tree. All that functionality comes in a compact and customizable recorder, which is attached to the browser or WPF application. The recorded steps have a lot of configurations to help you automate your application without writing code.

In this section you will learn in details about all features of the Test Studio Recorder. How to start it and how it can help you automate your application with stable and reliable tests. 

## Start Recording ##

There are two ways to initiate recording. You can either launch a new browser or WPF app instance with the compact recording toolbar attached, or you can attach the compact recording toolbar to an existing instance (applicable for IE only or WPF application). 

> **Note**
>
> To stop the recording session, close the browser or WPF application.

### Launch New Recording ###

1.&nbsp;  Open the test by double clicking on it. Click the **Record** button in the **Tests** tab or press **CTRL+R**.

<table id=no-table>
	<tr>
		<td>![Test Studio][1] <br><br>**Standalone version**</td>
		<td>![VS][2] <br><br>**VS plugin**</td>
	</tr>
<table>

2.&nbsp; Type the URL you want to navigate to or select it from recent URLs. Choose the recording browser (for web tests) and press Enter or the *Record* button in that window.

![Choose browser][3]

If you enable **Save my choice for the future** or set a preferred browser from the <a href="/general-information/test-execution/quick-execution" target="_blank">Test ribbon</a> the **Record** button will display the icon for the selected browser.

![Choose preferred browser][4]

3.&nbsp; Once the selected browser navigates to the specified URL or the WPF application is started, the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a> will attach to it. A navigate step is added in the Steps pane and you can continue recording the next actions as per the required scenario.

![Attached recorder][5]

> **Note**
> <br>
> Once a recording session is started **do not start another instance of the same browser or WPF application** until the session is finished!

### Attach to Existing Instance (Applicable for IR or WPF Application) ###

Click the drop-down arrow on the **Record** button to see a list of available IE browser instances or WPF applications. Select one to attach the recorder to that instance.

<table id=no-table>
	<tr>
		<td>![Attach to running browser][6] <br><br>**Web Test - Internet Explorer only**</td>
		<td>![Attach to running WPF instance][7] <br><br>**WPF Test - connect to running WPF application instance**</td>
	</tr>
<table>

## See also ##

* <a href="/features/recorder/compact-recording-toolbar" target="_blank">Compact Recording Toolbar</a>

[1]: /img/general-information/test-recording/overview/fig1.png
[2]: /img/general-information/test-recording/overview/fig2.png
[3]: /img/general-information/test-recording/overview/fig3.png
[4]: /img/general-information/test-recording/overview/fig4.png
[5]: /img/general-information/test-recording/overview/fig5.png
[6]: /img/features/recorder/test-recorder/fig6.png
[7]: /img/features/recorder/test-recorder/fig7.png
