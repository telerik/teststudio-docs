---
title: Record HTTP(S) Traffic
page_title: Record HTTP(S) Traffic
description: "Progress® Test Studio® for APIs - Record HTTP(S) Traffic"
position: 1
publish: true
---

# Record HTTP(S) Traffic

## Overview

With Progress® Test Studio® for APIs you can easily record your HTTP(S) traffic and create test steps against it. Click on the Record menu and choose Record HTTP Traffic.

![Record][1]

Or just click on the Record button in the toolbar.

![Record][10]

A new Recording HTTP Traffic tab is opened and the recording starts automatically.

![Record][11]

### HTTPS Recording

By default HTTPS decryption is disabled and you will not see any HTTPS traffic recorded.
If HTTP is all you need, you can just dismiss the warning message that will appear on top of the pane and keep using the feature.
If you need to capture HTTPS too, you can follow the
Settings link in the message or click on "File" >> "Settings" >> "Recording" to open the Recording Settings.

![Record][12]

In the Recording Settings you can configure the desired port for Test Studio to listen on as a system proxy. The default one is '8888'.
In the HTTPS section of the settings you can enable HTTPS decryption which will allow you to capture https traffic.
The first time you enable the "Decrypt HTTPS traffic" option,
you will usually see a warning message stating that the Root Certificate is not installed
(this warning might not appear if you already have [Fiddler](http://www.telerik.com/fiddler) installed
on your machine). Test Studio for APIs uses [FiddlerCore](http://www.telerik.com/fiddler/fiddlercore) to capture traffic and just like Fiddler,
needs its Root Certificate (it is named "DO_NOT_TRUST_FiddlerRoot") to be installed
which allows HTTPS traffic to be intercepted. To configure Windows to trust the Root Certificate click on the "Install Root Certificate" button.

![Record][13]

To install the certificate click Yes on the next dialog.

![Record][4]

> You can deny installing the certificate and Test Studio for APIs will still be able to capture HTTPS traffic.
A root certificate will still be generated in the Current User Certificate store
but it will not be registered as trusted. Therefore when you try loading https page in a browser you will see a warning for insecure connection like the one below.

![Record][14]

Once the recording is started, you will be able to view the captured traffic in the recording grid.

![Record][5]

You can now select individual session entries and add them to either an existing test step or to a new test case.
To do that, you can use the `Add Selected Sessions to Selected Test` and `Add Selected Sessions to a New Test` buttons.

![Record][6]

To stop recording press the stop button ![Record][7]. You also have the ability to delete a single session by using the trash icon ![Record][8] as well as to clear all sessions using the icon ![Record][9] .

> Please note that in case of application exit the ApiTesting may not deregister as a proxy which may interrupt your internet connection. For more information refer to <a href="/troubleshooting-guide/deregister-proxy">this article</a>.

[1]: /img/features/record/record-traffic-menu.png
[2]: /img/features/record/new-tab.png
[3]: /img/features/record/certificate.png
[4]: /img/features/record/certificate1.png
[5]: /img/features/record/capturing-traffic.png
[6]: /img/features/record/add-session.png
[7]: /img/features/record/stop-button.png
[8]: /img/features/record/trash.png
[9]: /img/features/record/clear-all.png
[10]: /img/features/record/record-traffic-toolbar.png
[11]: /img/features/record/https-disabled-message.png
[12]: /img/features/record/recording-settings.png
[13]: /img/features/record/root-certificate-warning.png
[14]: /img/features/record/browser-https-error.png
