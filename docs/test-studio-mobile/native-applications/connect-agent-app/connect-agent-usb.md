---
title: USB Connection
page_title: USB Connection
description: "USB Connection"
publish: true
previous_url: /test-studio-mobile/connect-agent-app/connect-agent-usb
position: 0
slug: ms-connect-agent-usb
---

# USB Connection

Once you have [installed]({% slug ms-install-agent-app%}) the Mobile Testing agent app, tap on it to launch it.

1. Tap on the **USB** button.

	![click USB](/img/test-studio-mobile/connect-agent-app/usb/fig1.png)

2. Specify the port and click **Done**.

	![specify port](/img/test-studio-mobile/connect-agent-app/usb/fig2.png)

3. [Create]({% slug ms-create-test%}) a **Mobile** test project in Test Studio and go to Connected Devices pane. Click **Connect Device** button.

	![connect device](/img/test-studio-mobile/connect-agent-app/usb/fig3.png)

	> Note that when one or more devices are connected, the button in the center of the screen is not shown and only the button in the upper left corner can be used to connect additional devices.

4. On the Connect a Device dialog that appears click on **Device** tab and then choose **USB Connection** option. The device should be recognized automatically. Simply verify the information, make sure the port which you selected in step 2 matches and click on the **+** icon to connect your device.

	![connect device](/img/test-studio-mobile/connect-agent-app/usb/fig4.png)

	> You can edit the port by double clicking on it.

5. Once successfully connected the device appear under the Connected Devices pane and the mobile testing agent displays the status that the device is connected and **Disconnect** button appears:

<table id="no-table">
	<tr>
	<td> ![device listed](/img/test-studio-mobile/connect-agent-app/usb/fig6.png) </td>
	<td> ![agent status](/img/test-studio-mobile/connect-agent-app/usb/fig7.png) </td>
	</tr>
<table>


> Please note in order to connect an iOS device you **MUST** have [iTunes](http://www.apple.com/itunes/) installed on the machine.


> For Samsung Android devices please make sure you have the Samsung USB drivers installed properly. You can download the drivers from [here](http://developer.samsung.com/technical-doc/view.do?v=T000000117).


> The Android devices should be in **development mode**.


See Also
--------

+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Record Android Test]({% slug ms-record-test-android%})
+ [Record Android Hybrid Test]({% slug ms-record-test-android-hybrid%})
+ [Record iOS Hybrid Test]({% slug ms-record-test-ios-hybrid%})
+ [Playback Tests]({% slug ms-quick-execution%})