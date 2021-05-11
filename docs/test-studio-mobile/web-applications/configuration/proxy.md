---
title: Configure Proxy
page_title: Configure Proxy
description: "Configure Proxy"
position: 1
slug: ms-webproxy
---

> To help you meet the demands of mobile users, Test Studio offers <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">responsive testing of web applications</a> enabling you to test your web application's layout, functionality and behavior on mobile and desktop browsers.
><br>
><br>
> Check out the <a href="/automated-tests/responsive/responsive-test" target="_blank">technical documentation for responsive application testing</a> in Test Studio.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

# Configure Proxy

> Before proceeding with the proxy configuration you must have [Test Studio Mobile Configuration]({% slug ms-configure-tsm%}) successfully set up.

## Configure Web Proxy On Mobile Devices

Test Studio Mobile uses a web proxy for injecting a web extension in every page that a web test navigates to. Before tests are recorded or executed, the web browser must be configured to route its traffic through Test Studio Mobile web proxy.

*	**Android Browsers**
	*	<a href="#android">Chrome (other)</a>
	*	<a href="#android-firefox">FireFox</a>

*	**iOS browsers**
	*	<a href="#ios">All browsers</a>


##Android

<a id="android"></a>
###Chrome (other)

1. On your mobile device tap **Settings -> WiFi**.

2. Long tap on connected network's name.

3. Modify Network Config -> Show Advanced Options.

4. Type the **Host** into the **Proxy host name** field and the **Port** into to the **Proxy port** field. Take the **Host** and **Port** values from the TestStudio Mobile agent configuration page on your device.

	![Configure proxy Android](/img/test-studio-mobile/web-applications/proxy/fig1.png)

5. Click **Save** in the settings dialog. Click the **Next** button in the browser.

6. Continue with [Install Certificate]({% slug ms-certificate%}) procedure.

<a id="android-firefox"></a>
###FireFox


1. Type **about:config** in your FifeFox mobile browser.

2. Search for Proxy and enter the **Host** and **Port** in the corresponding fields. Take the **Host** and **Port** values from the TestStudio Mobile agent configuration page on your device.

	*	**network.proxy.http** - Host
	*	**network.proxy.http_port** - Port

	![FF](/img/test-studio-mobile/web-applications/proxy/fig3.png)

3. Do the same for SSL connection and don't forget to set **Network Proxy Type** to 1.

	*	**network.proxy.ssl** - Host
	*	**network.proxy.ssl_port** - Port
	*	**network.proxy.type** - **set to 1**.

	![FF](/img/test-studio-mobile/web-applications/proxy/fig4.png)

4. After configuring the WiFI proxy settings click the **Next** button.

5. Continue with [Install Certificate]({% slug ms-certificate%}) procedure.

<a id="ios"></a>
##iOS

###All Browsers

1. Tap **Settings -> Wifi -> Tap the connected WiFi network**.

2. Tap the **Manual** option in the HTTP Proxy section.

3. Type **Host** into the **Server** field and the **Proxy** into to the **Port** field. Take the **Host** and **Port** values from the TestStudio Mobile agent configuration page on your device.

	![Configure proxy iOS](/img/test-studio-mobile/web-applications/proxy/fig2.png)

4. After configuring the WiFI proxy settings click the **Next** button.

5. Continue with [Install Certificate]({% slug ms-certificate%}) procedure.