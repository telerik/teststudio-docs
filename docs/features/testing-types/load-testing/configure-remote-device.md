---
title: Mobile Device Traffic
page_title: Mobile Device Traffic
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/load-testing/designing-load-tests/adding-user-profiles/capture-remote-traffic.aspx
position: 7
---
# Mobile Device Traffic


 In addition to capturing traffic from the local machine, you can also capture a user profile from a remote machine, including a mobile device. First, you must configure the remote device to connect to the Test Studio Load remote proxy. Here, we show how to connect a mobile device to your Load Testing remote proxy. Since Test Studio Load Testing uses the same proxy as Fiddler, you can configure your remote devices to connect to Test Studio Load Testing in the same way as connecting to Fiddler, but using port 9001.




- [Configure iOS](/features/testing-types/load-testing/configure-remote-device#configure-an-ios-device)
- [Configure Android](/features/testing-types/load-testing/configure-remote-device#configure-an-android-device)


## Configure an iOS Device

1.&nbsp; Tap **Settings > Wi-Fi**

![Wi Fi][1]

2.&nbsp; Tap ![info][2] for the Wi-Fi network of the Progress Test Studio Load Testing machine

![info][3]

3.&nbsp; Tap the **Manual** option in the **HTTP Proxy** section

![Manual][4]

4.&nbsp; In the Server box, type the IP address or hostname of your Test Studio Load Testing machine.

![Server][5]

5.&nbsp; In the **Port** box, type '9001'

![Port][6]

6.&nbsp; Ensure the Authentication slider is set to **Off**

![Auth][7]

## Configure an Android Device

1.&nbsp; Swipe down from the top of the screen and tap the **Settings** icon.

2.&nbsp; Tap **Wi-Fi**.

3.&nbsp; Tap and hold your current Wi-Fi network. Select **Modify Network**.

![Modify Network][8]

4.&nbsp; Tap the **Show advanced** options checkbox.

![Advanced][9]

5.&nbsp; Tap the **Proxy settings** drop-down menu and select **Manual**.

![Manual][10]

6.&nbsp; Type the IP address and port (usually 9001) of the Test Studio Load Testing machine.

![Port][11]

7.&nbsp; Tap **Save**.


Now you are ready to <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">capture traffic</a> from your remote device. 
<br>
<br>
**See Also**

- <a href="http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/MonitorRemoteMachine" target="_blank">Connect a remote machine to Fiddler</a>.

[1]: /img/features/testing-types/load-testing/configure-remote-device/fig1.png
[2]: /img/features/testing-types/load-testing/configure-remote-device/fig2.png
[3]: /img/features/testing-types/load-testing/configure-remote-device/fig3.png
[4]: /img/features/testing-types/load-testing/configure-remote-device/fig4.png
[5]: /img/features/testing-types/load-testing/configure-remote-device/fig5.png
[6]: /img/features/testing-types/load-testing/configure-remote-device/fig6.png
[7]: /img/features/testing-types/load-testing/configure-remote-device/fig7.png
[8]: /img/features/testing-types/load-testing/configure-remote-device/fig8.png
[9]: /img/features/testing-types/load-testing/configure-remote-device/fig9.png
[10]: /img/features/testing-types/load-testing/configure-remote-device/fig10.png
[11]: /img/features/testing-types/load-testing/configure-remote-device/fig11.png
