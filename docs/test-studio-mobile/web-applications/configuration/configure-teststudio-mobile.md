---
title: Configure Test Studio Mobile
page_title: Configure Test Studio Mobile
description: "Configure Test Studio Mobile"
position: 0
slug: ms-configure-tsm
---

# Configure Test Studio Mobile for Web testing

> The web testing configuration is a 4 step process. The first step is to configure the Test Studio Mobile project on the desktop machine.

1. Create a **Mobile** test project and [add a web test]({% slug ms-create-test%}).

2. Go to [project settings]({% slug ms-project-settings%}) and set the **Web proxy port** (the default is set to 8083). 

3. Click **Connect Device** under **Connected Device** pane. 

	![Connect Device](/img/test-studio-mobile/web-applications/connect-web-agent/fig2.png)

4. Choose the **Web Browser** tab.

	4.1 Click **Install** button to set the local HTTPS certificate.

	4.2 Using the mobile browser you want to test in go to the shown URL or scan the QR code. This will navigate you to the TestStudio Mobile agent configuration page on your device.

	![Navigate to URL](/img/test-studio-mobile/web-applications/connect-web-agent/fig3.png)

5. Continue with [Proxy Configuration]({% slug ms-webproxy%})