---
title: Native/Hybrid Applications
page_title: Native/Hybrid Applications
description: Getting Started article describing how to record and playback a mobile Test Studio test.
slug: ms-getting-started-native
tags: ios, testing, native, android, hybrid
publish: true
previous_url: /test-studio-mobile/overview-mb/native-applications,/test-studio-mobile/overview-mb
position: 1
---

> To help you meet the demands of mobile users, Test Studio offers <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">automated responsive testing</a> enabling you to test your web application's layout, functionality and behavior on mobile and desktop browsers.
><br>
><br>
> As of March 1, 2020, native mobile testing is __no longer supported__.

# Getting Started with Native/Hybrid iOS and Android Applications in Test Studio Mobile

This section walks you through the process of recording your first Test Studio Mobile native Android/iOS test and execute it on a physical device. Before you start, please ensure the following:

* You have access to a Windows machine where Test Studio Ultimate will be installed. The Test Studio Mobile solution currently works only on Windows machines and installs as part of the Test Studio product.
* iOS or Android running physical device. Testable app will be installed on this device. Mobile tests will be executed against this app.
* A Mac machine running Xcode is required to build and deploy the Demo App for iOS to a device.
* A machine running Eclipse or Android Studio to build and deploy the Demo App for Android to a device.
* Cordova CLI is required to be installed to build and deploy the Hybrid Demo App to a device.

## Agent App Installation

The Mobile Testing Agent app must be installed on a physical or virtual device that will execute tests against native/hybrid apps. The Agent app connects the testable app on the device with the machine where Test Studio Ultimate is installed.

* [Agent App Installation]({% slug ms-install-agent-app%})

## Connect Agent

After installing the Mobile Testing Agent app you should connect it to the Test Studio Mobile either by USB or Wi-Fi:

* [USB Connection]({% slug ms-connect-agent-usb%})

* [Wi-Fi Connection]({% slug ms-connect-agent-wifi%})

##Install a testable app to a device

You can either configure your app to be testable or use one of the pre-configured native Demo apps.

###Configure your app to be testable

* [Configure Android Native App]({% slug ms-configure-android%})

* [Configure iOS Native App]({% slug ms-configure-ios%})

* [Configure NativeScript App]({% slug ms-configure-nativescript%})

* [Configure Hybrid (AppBuilder) App]({% slug ms-configure-hybrid-appbuilder%})

* [Configure Hybrid (Cordova) App]({% slug ms-configure-hybrid%})

* [Configure Xamarin iOS App]({% slug ms-configure-xamarin-ios%})

 > Cordova, Xamarin and NativeScript apps eventually build native iOS/Android apps. As a result the configuration can be made either at the Xamarin/NativeScript level or at the final iOS/Android level.

###Build a pre-configured Demo app.

* [Run Demos]({% slug ms-run-demos%})

##Record and Playback Test

Once the above setup is complete you can start recording

* [Android Native]({% slug ms-record-test-android%}), [iOS Native]({% slug ms-record-test-ios%}), [Android Hybrid]({% slug ms-record-test-android-hybrid%}) or [iOS Hybrid]({% slug ms-record-test-ios-hybrid%}) test.

or 

* [Playback your test]({% slug ms-quick-execution%})


See Also
--------

+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})