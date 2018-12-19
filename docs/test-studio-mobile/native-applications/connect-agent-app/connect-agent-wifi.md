---
title: Wi-Fi Connection
page_title: Wi-Fi Connection
description: "Wi-Fi Connection"
publish: true
previous_url: /test-studio-mobile/connect-agent-app/connect-agent-wifi
position: 0
slug: ms-connect-agent-wifi
---

# Wi-Fi Connection

1. [Create]({% slug ms-create-test%}) a **Mobile** test project

2. After the project is created and loaded, go to the **Connected Devices** pane and click the **Connect Device** button

	![Connect a device](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig2.png)

3. From the opened pop-up window select the **Device** tab and then choose the **WiFi Connection** option. Copy the **Host** address and **Port** number that should be entered in the Test Studio Mobile Agent app

	![Configure host and port](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig3.png)

4. Once you have [installed]({% slug ms-install-agent-app%}) the Mobile Testing Agent app, tap on it to launch it:
 
 	Android

 	![Andorid mobile agent](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig4.png)

	iOS

	![iOS mobile agent](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig7.png)

5. Tap the Wi-Fi button and enter the **Host** and **Port** your message server is running on (copied in step 3 above). The message server is started automatically upon Test Studio Ultimate installation and runs by default on port 8084:

	Android

	![Adjust port](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig5.png)

	iOS

	![Adjust port](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig8.png)

6. Tap the **Connect** button, the agent connects to the server and its state changes to connected:

	Android

	![Connect](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig6.png)

	iOS

	![Connect](/img/test-studio-mobile/connect-agent-app/connect-agent-wifi/fig9.png)

7. You can now start recording or executing your tests.


See Also
--------

+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Record iOS Hybrid Test]({% slug ms-record-test-ios-hybrid%})
+ [Record Android Test]({% slug ms-record-test-android%})
+ [Record Android Hybrid Test]({% slug ms-record-test-android-hybrid%})
+ [Playback Tests]({% slug ms-quick-execution%})