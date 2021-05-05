---
title: Hybrid (AppBuilder)
page_title: Hybrid (AppBuilder) app Testing
description: Apply our testing extension to your AppBuilder application.
slug: ms-configure-hybrid-appbuilder
tags: appbuilder testing, hybrid
publish: true
position: 4
---

> Although the Mobile testing module is in the process of discontinuation, Test Studio main product continues supporting <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">responsive mobile testing for web applications</a> to help meeting the demand of mobile users.

#Configure your AppBuilder app to be testable.

> Setting up your app for testing with Telerik Mobile Testing plugin requires that you disable the Analytics plugin which is enabled by default in some of the AppBuilder app templates.

Follow the step-by-step instructions below to create a new sample AppBuilder hybrid app, add the Telerik Mobile Testing plugin to it, and execute sample tests against it.

* [Create AppBuilder hybrid sample app](#CreateApp)
* [Build and deploy the app](#PhysicalDevices)

## Create AppBuilder sample hybrid app <a id="CreateApp" name="CreateApp"></a>

1. To create an AppBuilder sample hybrid app, an [account in the Telerik Platform][1] is needed. Once logged in, create a new app by clicking on the **Create App** button.

  ![Create App](/img/test-studio-mobile/configure-your-app/configure-appbuilder/CreateApp.png)

2. Select **Advanced** tile. For the purpose of this tutorial we will use the Airlines demo application from the **Samples and templates** option. Let's name the app `MySampleApp` and click the **CreateApp** button.

  ![Create App Name](/img/test-studio-mobile/configure-your-app/configure-appbuilder/CreateAppName.png)

3. The next step is to enable the Telerik Mobile Testing plugin and set the app's configuration variable to match the app identifier. To do this, double-click **Properties** in the solution explorer and then go to **Plugins**. Scroll to the bottom and enable the Telerik Mobile Testing plugin. If Telerik Mobile Testing is not in the list, add it from the plugin marketplace by clicking on the **Install from Plugins Marketplace** button. Finally expand the plugin and click on the **Configuration variables** button. Enter the iOS app identifier that you will use in your iOS hybrid tests. 

  ![Set Ios Identifier](/img/test-studio-mobile/configure-your-app/configure-appbuilder/SetIosIdentifier.png)

  <a name="appid"></a>
 > In your iOS hybrid tests the app identifier for an iOS app must match the IOS_APP_URL entered in the **Configuration variables** dialog, and suffixed with **://** . For example **airlinessampleapp://**.

 > The **Configuration variables** window sets only the iOS variable. The Android variable is set by default in the `General` settings and can be changed from there (see below).

 <!--- > When automation against `WKWebView` views is targeted, additional set of plugins is required. Click on **Install from Plugins Marketplace** button, and search for **Mobile Testing Extension - WebKit** and **WKWebView Polyfill** plugins. 

 > When automation against `Crosswalk WebView` views is targeted, additional set of plugins is required. Click on **Install from Plugins Marketplace** button, and search for **Mobile Testing Extension - XWalkView** and **Crosswalk WebView Engine** plugins. --->

4. Go to **General** settings and verify the Application Identifier matches the Android app identifier that you will use in your tests.

  ![Set Android Identifier.png](/img/test-studio-mobile/configure-your-app/configure-appbuilder/SetAndroidIdentifier.png)

## Build and deploy the app.<a id="PhysicalDevices" name="PhysicalDevices"></a>

1. To build the app click **Run**, then **Build** and choose the Android or iOS app package. For iOS builds you need to have your private identity and provisioning profile correctly setup.

  Android

  ![Build Android](/img/test-studio-mobile/configure-your-app/configure-appbuilder/BuildAndroid.png)

  iOS

  ![Build iOS](/img/test-studio-mobile/configure-your-app/configure-appbuilder/BuildIos.png)

2. After a successful build, the app can be downloaded (iOS & Android) or QR scanned (Android) and installed.

  Android

  ![Download Android](/img/test-studio-mobile/configure-your-app/configure-appbuilder/DownloadAndroid.png)

  iOS

  ![Download Ios](/img/test-studio-mobile/configure-your-app/configure-appbuilder/DownloadIos.png)

3. Now that you have the app configured for testing, the next step is to [create]({% slug ms-create-test%}) and then record an [Android]({% slug ms-record-test-android-hybrid%}) or [iOS]({% slug ms-record-test-ios-hybrid%}) hybrid test.

## See Also

* [Agent App instalation]({% slug ms-install-agent-app%})
* [Connect Agent App WiFi]({% slug ms-connect-agent-wifi%})
* [Connect Agent App USB]({% slug ms-connect-agent-usb%})
* [Create Test]({% slug ms-create-test%})
* [Record Android Hybrid test]({% slug ms-record-test-android-hybrid%})
* [Record iOS hybrid test]({% slug ms-record-test-ios-hybrid%})


[1]:http://docs.telerik.com/platform/help/accounts/accounts
