---
title: Message Server
page_title: Message Server
description: Message Server
slug: ms-message-server
tags: message server
publish: true
position: 8
previous_url: /test-studio-mobile/getting-started-mb/message-server
---

#Message Server

Test Studio Mobile allows the user to write tests on a desktop machine and then execute them on a mobile device. The communication between the desktop runner and the device's agent is based on exchanged JSON messages. A piece of sofware called **Message Server** is responsible for handling these messages. 

## Default Execution

The Message Server is a node.js application that starts automatically behind the scenes when Test Studio **mobile** project is opened in the Test Studio GUI. It runs on the same machine where Test Studio is run and can be accessed on the machine's host/IP address and port [selected by the user]({% slug ms-project-settings%}) - **the default is 8084**. Because message server is responsible for the entire communication between test runner and agents, Test Studio also connects to it right after a mobile project is opened. 

In the Test Studio GUI, the message server current status can be verified at the bottom left corner. If, for some reason, Test Stuido can't connect to the message server, a red dot indicattor is presented. Click **Edit Settings** to show the Message Server Settings dialog where its host and port can be edited:

![message server disconnected](/img/test-studio-mobile/getting-started-mb/message-server/fig1.png)

Enter valid and available host and port values and click the **Restart** button to restart and connection to the message server. 

![message server connected](/img/test-studio-mobile/getting-started-mb/message-server/fig2.png)

 > Message server settings can also be edited from the [project settings dialog]({% slug ms-project-settings%})

Once Test Studio is connected to a running instance of the message server, you can connect your native ([USB]({% slug ms-connect-agent-usb%}) and [Wi-Fi]({% slug ms-connect-agent-wifi%})) or [web]({% slug ms-configure-tsm%}) agents.

## Standalone Execution

The Message Server can be started even if Test Studio GUI doesn't run at all. The stand-alone version is include in the Mobile Runtime package and can be run on Windows, Mac and Linux machines:

1. [Download]({% slug ms-download%}#4-Mobile-Runtime) the Mobile Runtime package for the intended platform and unpack it.
2. Open a command window and navigate to the unpacked folder location. Navigate to the `MessageServer` folder.
3. For Windows execute the `msgsrv-ctl.bat` file. For Mac/Linux execute the `msgsrv-ctl.sh` file. This will show you the available options for message server CLI. 

	Windows

	![message server menu](/img/test-studio-mobile/getting-started-mb/message-server/menu_windows.png)

	Mac

	![message server menu](/img/test-studio-mobile/getting-started-mb/message-server/menu_mac.png)

	Linux

	![message server menu](/img/test-studio-mobile/getting-started-mb/message-server/menu_linux.png)

4. Calling the `start` command will launch a stand-alone message server on the default port 8084.

	Windows

	![message server start default](/img/test-studio-mobile/getting-started-mb/message-server/start_windows_default.png)

	Mac

	![message server start default](/img/test-studio-mobile/getting-started-mb/message-server/start_mac_default.png)

	Linux

	![message server start default](/img/test-studio-mobile/getting-started-mb/message-server/start_Linux_default.png)

5. The stand-alone Message Server CLI allows usage of any available port in the range bewteen 1025 and 65535. Just specify it as an option to the `start` command:

	Windows

	![message server start custom](/img/test-studio-mobile/getting-started-mb/message-server/start_windows_custom.png)

	Mac

	![message server start custom](/img/test-studio-mobile/getting-started-mb/message-server/start_Mac_custom.png)

	Linux

	![message server start custom](/img/test-studio-mobile/getting-started-mb/message-server/start_Linux_custom.png)


Once the message server is started, you can start connecting native Android and iOS agents to it using [Wi-Fi]({% slug ms-connect-agent-wifi%}) or [USB]({% slug ms-connect-agent-usb%}) connections.

 > The stand-alone version of the Message Server doesn't stop automatically. You will need to call the `stop` command of the Message Server CLI after you finish your work with it. To check the current status of the server, call the CLI's `status` command.

See Also
--------

+ [System Requirements]({% slug ms-requirements%})
+ [Downloads]({% slug ms-download%})