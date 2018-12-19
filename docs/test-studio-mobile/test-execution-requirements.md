---
title: System Requirements
page_title: System Requirements
description: "Test Studio Mobile System Requirements"
position: 0
slug: ms-requirements
previous_url: /test-studio-mobile/test-execution-requirements-mb
---
#System Requirements

##Test Recording

To utilize the codeless point and click test recording, a Windows 7+ machine running Test Studio Mobile is needed. Currently, Test Studio Mobile comes as part of the Test Studio Ultimate bundle and can't be installed on Mac machines. Test recording requires at least 1 connected Native or Web test agent (see bellow).

##Test Execution

Test execution requires at least 1 connected Native or Web test agent (see bellow).

* Windows 7+ machines - tests can be executed either by the Test Studio Mobile GUI or Mobile Testing Test Runner CLI for Windows.
* Mac OS X 10.8+ machines - tests can be executed only by the Mobile Testing Test Runner CLI for Mac and Linux. 
* Linux Ubuntu 14+ machines - tests can be executed only by the Mobile Testing Test Runner CLI for Mac and Linux.

##Test Agent for Native/Hybrid Applications

When a native or hybrid app is to be tested, test agent is the Mobile Testing Agent app for Android or iOS:

###Android Native/Hybrid

*	Install the Mobile Testing Agent app for Android on a device/emulator running Android 4+ 

###iOS Native/Hybrid

*	Install the Mobile Testing Agent app for iOS on a Device/simulator running iOS 8+

##Test Agent for Web Applications

When a web app is to be tested, test agent is the browser itself (mobile or desktop). The browser must support WebSockets. Bellow is a short list of browsers that support WebSockets:

*	iOS Safari 6.0+

*	Android Browser 4.4+

*	Chrome for Android 32.0+

*	Firefox for Android 26.0+

*	[See more](http://caniuse.com/#search=websocket)

##Native Demo apps

Preconfigured Native demo apps for Android and iOS are available for download. Building and deploying those apps require:

*	Windows 7+ and Android Studio 0.4.0+ to deploy provided Android Demo Application
*	Mac OS X 10.8+ and Xcode 6+ to deploy provided iOS Demo Application

##Hybrid Demo app

Preconfigured Hybrid demo app (Cordova) is available for download. Building and deploying that app require:

*   Cordova CLI

##Mobile Testing Test Runner CLI

*	Windows 7+ machines - Mobile Testing Test Runner CLI installs as part of Test Studio Mobile. 
*	Mac OS X 10.8+ machines - Mobile Testing Test Runner CLI can be downloaded and run separately and requires Mono to be installed on the Mac.
*	Linux machines running Ubuntu 14+ - Mobile Testing Test Runner CLI can be downloaded and run separately and requires Mono to be installed on the machine.