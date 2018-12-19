---
title: Record Android Test
page_title:  Record Android Test
description: "Record a Test Studio Mobile test"
publish: true
slug: ms-record-test-android
previous_url: /test-studio-mobile/test-recording/record-test
position: 0
slug: ms-record-test-android
---

#Record an Android Test

Once the native Mobile Testing Agent app is [connected]({% slug ms-getting-started-native%}#Connect-Agent) to Test Studio Mobile the devices are listed in the **Conencted Devices** pane.

1. Open an Android test to enable the recording buttons. 

	![Record Android](/img/test-studio-mobile/test-recording/record-test/fig8.png)

2. Clicking on any of the **Record** buttons, shows a dialog where `Application Identifier` must be selected. The app identifier is setup during the [Android instrumentation process]({% slug ms-configure-android%}) of the testable app. The [Demo App]({% slug ms-run-demos%}#Android-Demo-App) is already setup with the **com.telerik.demoapplication** identifier.

	![Android APP identifier](/img/test-studio-mobile/test-recording/record-test/fig5.png)

3. Clicking the **Start** button disconnects the Agent app and launches the Demo App. The test recorder is attached and any gestures or actions you perform over the launched Demo App is recorded as steps in the Test Studio test

	![Android App](/img/test-studio-mobile/test-recording/record-test/fig6.png)

	**Note:** Additional steps (e.g. verifications) can be added through the [Step Builder]({% slug ms-step-builder%}).

4. Once the test is complete, stop recording by clicking on the **Stop Record** button. The recorder is detached, the Demo App is closed and the Agent app is returned in connected state.

	![Stop recording Android App](/img/test-studio-mobile/test-recording/record-test/fig7.png)

## See also

* [Create a test]({% slug ms-create-test%})
* [Connect agent USB]({% slug ms-connect-agent-usb%})
* [Connect agent Wi-Fi]({% slug ms-connect-agent-wifi%})