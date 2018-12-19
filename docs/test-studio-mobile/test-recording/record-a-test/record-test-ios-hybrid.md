---
title: Record iOS Hybrid Test
page_title:  Record iOS Hybrid Test
description: "Record a Test Studio Mobile test"
publish: true
position: 4
slug: ms-record-test-ios-hybrid
---

#Record an iOS Hybrid Test

Once the native Mobile Testing Agent app is [connected]({% slug ms-getting-started-native%}#Connect-Agent) to Test Studio Mobile the devices are listed in the **Conencted Devices** pane.

1. Open an iOS Hybrid test to enable the recording buttons. 

	![Record iOS Hybrid](/img/test-studio-mobile/test-recording/record-test/fig13.png)

2. Clicking on any of the **Record** buttons, shows a dialog where `Application Identifier` must be entered. The app identifier is:
	* For AppBuilder app, it is set during AppBuidler app [configuration process]({% slug ms-configure-hybrid-appbuilder%}#appid).
	* For Cordova app, it is set in the Cordova CLI during the [Cordova App creation process]({% slug ms-configure-hybrid%}#App-Identifier) and is something like **telerikmt1**.
	* For the [Demo Hyrbid App]({% slug ms-run-demos%}#Android-Hybrid-Demo-App), it is already setup with the **telerikmt1** identifier for iOS.

	![iOS Hybrid APP identifier](/img/test-studio-mobile/test-recording/record-test/fig14.png)

3. Clicking the **Start** button disconnects the Agent app and launches the testable app. The test recorder is attached and any gestures or actions you perform over the launched testable app are recorded as steps in the Test Studio test

	![iOS App](/img/test-studio-mobile/test-recording/record-test/fig15.png)

	> Additional steps (e.g. verifications) can be added through the [Step Builder]({% slug ms-step-builder%}).

4. Once the test is complete, stop recording by clicking on the **Stop Record** button. The recorder is detached, the testable app is closed and the Agent app is returned in connected state.

	![Stop recording iOS App](/img/test-studio-mobile/test-recording/record-test/fig16.png)

## See also

* [Create a test]({% slug ms-create-test%})
* [Connect agent USB]({% slug ms-connect-agent-usb%})
* [Connect agent Wi-Fi]({% slug ms-connect-agent-wifi%})

[1]: https://cordova.apache.org/docs/en/latest/guide/cli/index.html