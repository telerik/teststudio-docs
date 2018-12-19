---
title: Downloads
page_title: Downloads
description: Mobile Testing Downloads
slug: ms-download
tags: ios, android, wp, testing, download
publish: true
previous_url: /test-studio-mobile/installation/download
position: 2
---

# Pick your download

## 1. Mobile Testing Agent App

The Mobile Testing Agent app must be installed on physical or virtual devices that will execute tests against native or hybrid apps. This app connects Test Studio Mobile and the actual testable app. Read [this article]({% slug ms-install-agent-app%}) for more information.

  * [Mobile Testing Agent app for iOS](https://itunes.apple.com/us/app/mobile-testing/id787441509?ls=1&amp;mt=8) - required to execute native tests on an iOS device.

  * [Mobile Testing Agent app for Android](https://play.google.com/store/apps/details?id=com.telerik.testing.executionagent) - required to execute native tests on an Android device.

## 2. Extensions

Native/Hybrid apps must be configured in order to be testable by Test Studio Mobile. Configuring requires adding a platform specific Test Studio Mobile extension to the app. Read the dedicated [Android]({% slug ms-configure-android%}), [iOS]({% slug ms-configure-ios%}) and [Hybrid (Cordova)]({% slug ms-configure-hybrid%}) articles for more information.

* [Android extension](/samples/MobileTestingExtension_Android.zip)

* [iOS extension](/samples/MobileTestingExtension_iOS.zip)

* [Hybrid extension](/samples/MobileTestingExtension_Hybrid.zip)

## 3. Demo Apps

Demo apps are preconfigured native/hyrbid apps for testing with Test Studio Mobile. Read [this article]({% slug ms-run-demos%}) for more information.

* [Android demo app](/samples/androidDemoApplication.zip)

* [iOS demo app](/samples/xCodeDemoApplication.zip)

* [Hybrid (Cordova) demo app](/samples/cordovaDemoApplication.zip)

## 4. Mobile Runtime

The Mobile Runtime package is dedicated to test execution only. It consists of stand-alone versions of the tools that are required for test execution - Message Server and Mobile Testing Runner CLI.

### Message Server

Read [this article]({% slug ms-message-server%}) for more information about what Message Server is and how it works. By default, this server installs as part of Test Studio Mobile installation and starts automatically behind the scenes when Test Studio mobile project is opened in the GUI. However, a stand-alone version of the Message Server can be started even if Test Studio Mobile GUI doesn't run at all. The stand-alone version is part of the Mobile Runtime package that is available for Windows, Mac and Linux.

### Mobile Testing Runner CLI

Read [this article]({% slug ms-test-runner%}) for more information about what Mobile Testing Runner CLI is and how it works. By default, this CLI runner installs as part of Test Studio Mobile installation and starts automatically behind the scenes when Test Studio mobile project is opened in the GUI. However, a stand-alone version of the Mobile Testing Runner CLI can be started even if Test Studio Mobile GUI doesn't run at all. The stand-alone version is part of the Mobile Runtime package that is available for Windows, Mac and Linux.  

* [Mobile Runtime for Windows](/samples/MobileRuntime-Windows.zip)
* [Mobile Runtime for Mac](/samples/MobileRuntime-MacOs.zip)
* [Mobile Runtime for Linux](/samples/MobileRuntime-Linux.zip)

## 5. Demo Test Project

A sample Test Studio Mobile project containing tests running against the Demo Apps. Read [this article]({% slug ms-quick-execution%}) for more information about how to execute the tests.

* [Demo project](/samples/DemoMobileProject.zip)


See Also
--------

+ [Agent App Installation]({% slug ms-install-agent-app%})
+ [Run Demos]({% slug ms-run-demos%})