---
title: Agent App Installation
page_title: Agent App Installation
description: How to install agent to an iOS simulator
previous_url: /test-studio-mobile/installation/agent-app-installation
position: 2
slug: ms-install-agent-app
---
# Agent App Installation

## Overview

The Mobile Testing Agent app must be installed on physical or virtual devices that will execute tests against native or hybrid apps. This app connects the machine where Test Studio Mobile is installed and the actual testable app.

## Install to a real device

Mobile Testing Agent app can be installed for free from [AppStore](https://itunes.apple.com/us/app/mobile-testing/id787441509?ls=1&amp;mt=8) or [Google Play](https://play.google.com/store/apps/details?id=com.telerik.testing.executionagent). Search for `Mobile Testing` and install the app to any supported device aimed for testing.

## Install to an Android emulator

1. Create an Android emulator with the [AVD Manager](http://developer.android.com/tools/devices/managing-avds.html).

2. [Download](/samples/MobileTestingExtension_Android.zip) the Test Studio Mobile extension for Andorid and unpack it. Find the `MobileTesting.apk` file.

3. Open a new command window.

4. Open the Android SDK subfolder: /sdk/platform-tools.

* ### OS X

	1. Type ./adb devices to see a list of connected devices.

	2. Type ./adb -s DEVICE_ID install "\path\to\MobileTesting.apk"

		where DEVICE_ID is the target device or emulator.

		![Device ID](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig1.png)

* ### Windows

	1. Type adb devices to see a list of connected devices.

	2. Type adb -s DEVICE_ID install "\path\to\MobileTesting.apk"

		where DEVICE_ID is the target device or emulator.

		![Device ID Windows](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig2.png)


## Install on iOS simulator

1. Open a new command window.

2. [Download](/samples/MobileTestingAgentForSimulator.zip) the Test Studio Agent App package for iOS and unpack it. Find the `MobileTestingSimulator.app` folder.

* ###Using Xcode 6

	1. To get a list of all available simulators type: *xcrun simctl list*

		![Install app agent](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig4.png)

	2. Choose a device and boot it if it is not already.

		![Boot simulator](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig5.png)

* ###Using Xcode 7

	1. Open the Spotlight search and type *Simulator* to find the Simulator app and start it.

		![Open Spotlight](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig6.png)

Once a simulator is booted, install the `MobileTesting.app` to it by the following terminal command.

![Install agent](/img/test-studio-mobile/getting-started-mb/agent-app-installation/fig7.png)


See Also
--------

+ [Downloads]({%slug ms-download%})
+ [Run Demos]({%slug ms-run-demos%})