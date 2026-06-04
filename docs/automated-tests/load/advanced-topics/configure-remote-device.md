---
title: Mobile Device Traffic
page_title: Mobile Device Traffic
description: "Configure Test Studio to capture user profile http traffic from a remote machine, including a mobile device"
position: 3
---
# Mobile Device Traffic

 In addition to capturing traffic from the local machine, you can also capture a user profile from a remote machine, including a mobile device. First, you must configure the remote device to connect to the Test Studio Load remote proxy. Here, we show how to connect a mobile device to your Load Testing remote proxy. Since Test Studio Load Testing uses the same proxy as Fiddler, you can configure your remote devices to connect to Test Studio Load Testing in the same way as connecting to Fiddler, but using port 9001.

- [Configure iOS](/features/testing-types/load-testing/configure-remote-device#configure-an-ios-device)
- [Configure Android](/features/testing-types/load-testing/configure-remote-device#configure-an-android-device)

## Configure an iOS Device

1. Tap **Settings > Wi-Fi**

    ![Wi Fi](/img/features/testing-types/load-testing/configure-remote-device/fig1.png)

2. Tap ![info](/img/features/testing-types/load-testing/configure-remote-device/fig2.png) for the Wi-Fi network of the Progress Test Studio Load Testing machine

    ![info](/img/features/testing-types/load-testing/configure-remote-device/fig3.png)

3. Tap the **Manual** option in the **HTTP Proxy** section

    ![Manual](/img/features/testing-types/load-testing/configure-remote-device/fig4.png)

4. In the Server box, type the IP address or hostname of your Test Studio Load Testing machine.

    ![Server](/img/features/testing-types/load-testing/configure-remote-device/fig5.png)

5. In the **Port** box, type '9001'

    ![Port](/img/features/testing-types/load-testing/configure-remote-device/fig6.png)

6. Ensure the Authentication slider is set to **Off**

    ![Auth](/img/features/testing-types/load-testing/configure-remote-device/fig7.png)

## Configure an Android Device

1. Swipe down from the top of the screen and tap the **Settings** icon.

2. Tap **Wi-Fi**.

3. Tap and hold your current Wi-Fi network. Select **Modify Network**.

    ![Modify Network](/img/features/testing-types/load-testing/configure-remote-device/fig8.png)

4. Tap the **Show advanced** options checkbox.

    ![Advanced](/img/features/testing-types/load-testing/configure-remote-device/fig9.png)

5. Tap the **Proxy settings** drop-down menu and select **Manual**.

    ![Manual](/img/features/testing-types/load-testing/configure-remote-device/fig10.png)

6. Type the IP address and port (usually 9001) of the Test Studio Load Testing machine.

    ![Port](/img/features/testing-types/load-testing/configure-remote-device/fig11.png)

7. Tap **Save**.


Now you are ready to <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">capture traffic</a> from your remote device. 
<br>
<br>
**See Also:**

- <a href="http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/MonitorRemoteMachine" target="_blank">Connect a remote machine to Fiddler</a>.

