---
title: Hybrid (Cordova)
page_title: Hybrid (Cordova) app Testing
description: Apply testing extension to a Hybrid (Cordova) application.
slug: ms-configure-hybrid
tags: cordova testing, hybrid
publish: true
position: 5
---

> To help you meet the demands of mobile users, Test Studio offers <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">automated responsive testing</a> enabling you to test your web application's layout, functionality and behavior on mobile and desktop browsers.
><br>
><br>
> As of March 1, 2020, native mobile testing is __no longer supported__.

#Configure your Hybrid app (Cordova) to be testable

  > The application configured following the steps below, should be used for testing purposes only and will not be accepted in Apple App Store and Google Play Store. 

Since building Hybrid mobile applications produce native iOS and Android apps, they can be easily tested with Test Studio Mobile. [This getting-started article]({% slug ms-getting-started-native%}) provides more details about testing native iOS and Android apps.


## Create a hybrid Cordova app

Follow the standard flow for creating hybrid Cordova app described [here][1].

## Add Extension

1. [Download](/samples/MobileTestingExtension_Hybrid.zip) the Test Studio Mobile extension for Hybrid apps and unpack it.
2. After a hybrid app is created navigate to app's containing folder and add the extension:

		cordova plugin add "Path to `com.telerik.mobiletesting` folder"

	![Mobile Testing Extension](/img/test-studio-mobile/configure-your-app/configure-hybrid/mobile-testing-extension.png)

 > Type `cordova plugin` to list all added plugins and verify the `Mobile Testing Extension` plugin is added.

## App Identifier

To successfully test a Condova hybrid app, Test Studio Mobile needs to know the app identifier. It is set like this:

* Android - the App Identifier for Android is set during app creation in the Cordova CLI (see **Create a hybrid Cordova app** above) and looks something like **com.mycompany.myapp**.
* iOS - the App Identifier for iOS comes from the Test Studio Mobile extension for iOS (see **Add Extension** above). By default this extension sets **telerikmt1** to be the App Identifier for iOS. To change it in the extension before it is added to the app, navigate to the folder of the downloaded extension (`com.telerik.mobiletesting`) and open the **plugin.xml** file in your preferred text editor. Locate the App Identifier as shown below and cahnge it:

![Mobile Testing AppId iOS](/img/test-studio-mobile/configure-your-app/configure-hybrid/pluginxml-ios.png)

 > If you deploy the app to an **iOS 9** device then you must use one of the names listed below:
* telerikmt1
* telerikmt2
* telerikmt3
* telerikmt4
* telerikmt5
* telerikmt6
* telerikmt7
* telerikmt8
* telerikmt9
* telerikmt10
* tsdemoapplication

## Build and deploy the app

To complete the app, follow the [Cordova Command-line Interface][1] guide to add required platforms and deploy to devices or emulators.

See Also
--------

+ [Record Android Hybrid Test]({% slug ms-record-test-android-hybrid%})
+ [Record iOS Hybrid Test]({% slug ms-record-test-ios-hybrid%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})

[1]: https://cordova.apache.org/docs/en/latest/guide/cli/index.html