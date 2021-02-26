---
title: Recording Toolbar
page_title: Recording Toolbar
description: "Test Studio Recording Toolbar. Test Studio recorder is attached to the browser wpf application. DOM explorer in the Test Studio recorder. Step builder in the Test Studio recorder"
previous_url: /user-guide/recording-tests/recording-toolbar.aspx, /user-guide/recording-tests/recording-toolbar
position: 1
---
# Recording Toolbar #

Once a recording session is started the ***Recorder Toolbar*** gets connected to the browser/WPF application instance.

![Attaching the recorder][1]

## DOM Explorer Options ##

Below are listed its features related to the <a href="/features/recorder/dom-explorer" target="_blank">DOM explorer</a> and how you could use these during recording:

<table id="no-table" >
	<tr cellspacing="10">
		<td cellspacing="1">![Enable/Disable Hover Over Highlighting][2]<br></td>
		<td>**Enable/Disable Hover Over Highlighting** (Use keyboard shortcut -press "*Pause/Break*" button to toggle)</td>
	</tr>
	<tr cellspacing="10">
		<td>![Pause Recording][3]</td>
		<td>**Pause Recording** (Use keyboard shortcut - press "*Print Screen*" button to toggle)</td>
	</tr>
	<tr>
		<td>![Start Recording][4]</td>
		<td>**Start Recording** (Use keyboard shortcut - press "*Print Screen*" button to toggle)</td>
	</tr>
	<tr>
		<td>![Reconnect Recorder][5]
		<td>**Reconnect Recorder** - Restores communication between Test Studio and the recording browser window or WPF app, if necessary</td>
	</tr>
	<tr>
		<td>![Navigation panel][6]</td>
		<td>**Navigation panel** - Type URL to record and navigate to, Refresh the Browser, use the arrows to navigate Back or Forward</td>
	</tr>
	<tr>
		<td>![Dock/Undock][7] / ![Dock/Undock][8]</td>
		<td>**Undock/Dock** - Undock the recorder toolbar from the browser/WPF window or dock it back</td>
	</tr>
	<tr>
		<td>![Add to elements repository][9]</td>
		<td>**Add To Elements Repository** - Add a single or multiple elements to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>)</td>
	</tr>
	<tr>
		<td>![Manual Refresh of the DOM][12]</td>
		<td>**Manual Refresh of the DOM** - Used when auto-refresh is paused and the DOM tree is changed</td>
	</tr>
	<tr>
		<td>![Freeze DOM tree][11] / ![Unfreeze DOM tree][11a]</td>
		<td>**Freeze/Unfreeze DOM tree** - Pause/Resume the DOM tree auto-refresh option</td>
	</tr>
	<tr>
		<td>![Elements tree/tag view][10]</td>
		<td>**Elements Tree/Tag View** - Whether to display the elements as tree view or tag view</td>
	</tr>
<table>

## Step Builder Options ##

On the right side of the recording toolbar you can find the ***Actions*** and ***Verifications*** steps from the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a>. Adding steps during recording is necessary in some special occasions - if you need a <a href="/features/recorder/mouse-actions/drag-and-drop" target="_blank">drag&drop step</a> or an <a href="/features/recorder/verifications/advanced-verification" target="_blank">advanced verification</a>.

Other possible scenarios when is recommended to use the Step Builder from the **Recorder Toolbar** are usually related to specific applications and how these are built. If *Record&Playback* doesn't work out of the box usually the structure of application does not allow recognition of separate elements identified by unique attributes. Then the only option left is to manually select the correct element in DOM explorer and add the necessary steps.

**See also:**

* <a href="/features/elements-menu/overview" target="_blank">Elements Menu</a>

* <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>

* <a href="/features/verifications/overview" target="_blank">Verifications</a>

[1]: /img/general-information/test-recording/recording-toolbar/fig1.png
[2]: /img/general-information/test-recording/recording-toolbar/fig2.png
[3]: /img/general-information/test-recording/recording-toolbar/fig3.png
[4]: /img/general-information/test-recording/recording-toolbar/fig4.png
[5]: /img/general-information/test-recording/recording-toolbar/fig5.png
[6]: /img/general-information/test-recording/recording-toolbar/fig6.png
[7]: /img/general-information/test-recording/recording-toolbar/fig7.png
[8]: /img/general-information/test-recording/recording-toolbar/fig8.png
[9]: /img/general-information/test-recording/recording-toolbar/fig9.png
[10]: /img/general-information/test-recording/recording-toolbar/fig10.png
[11]: /img/general-information/test-recording/recording-toolbar/fig11-lock.png
[11a]: /img/general-information/test-recording/recording-toolbar/fig11-unlock.png
[12]: /img/general-information/test-recording/recording-toolbar/fig12-refresh.png
