---
title: Record iOS Test
page_title:  Record iOS Test
description: "Record a Test Studio Mobile test"
publish: true
position: 1
slug: ms-record-test-ios
---

#Record an iOS Test

Once the native Mobile Testing Agent app is [connected]({% slug ms-getting-started-native%}#Connect-Agent) to Test Studio Mobile the devices are listed in the **Conencted Devices** pane.

1. Open an iOS test to enable the recording buttons. 

	![Record iOS](/img/test-studio-mobile/test-recording/record-test/fig1.png)

2. Clicking on any of the **Record** buttons, shows a dialog where `Application Identifier` must be selected. The app identifier is setup during the [iOS instrumentation process]({% slug ms-configure-ios%}) of the testable app. The [Demo App]({% slug ms-run-demos%}#iOS-Demo-App) is already setup with the **tsdemoapplication://** identifier.

 	> When used in Test Studio, the `Application Identifier` setup in Xcode must be suffixed with **://**. For example, the app identifier that is setup for the Demo app in Xcode is **tsdemoapplication** (no trailing colon and slashes), but suffixed with **://** when entered in the Test Studio **Set Application ID** dialog.

	![iOS App](/img/test-studio-mobile/test-recording/record-test/fig2.png)

3. Clicking the **Start** button disconnects the Agent app and launches the Demo App. The test recorder is attached and any gestures or actions you perform over the launched Demo App is recorded as steps in the Test Studio test:

	![iOS App](/img/test-studio-mobile/test-recording/record-test/fig3.png)

	**Note:** Additional steps (e.g. verifications) can be added through the [Step Builder]({% slug ms-step-builder%}).

4. Once the test is complete, stop recording by clicking on the **Stop Record** button. The recorder is detached, the Demo App is closed and the Agent app is returned in connected state.

	![iOS App](/img/test-studio-mobile/test-recording/record-test/fig4.png)
 
## See also

* [Create a test]({% slug ms-create-test%})
* [Connect agent USB]({% slug ms-connect-agent-usb%})
* [Connect agent Wi-Fi]({% slug ms-connect-agent-wifi%})