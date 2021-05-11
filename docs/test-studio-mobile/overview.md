---
title: Overview
page_title: Test Studio Mobile Overview
description: "Overview of Test Studio Mobile"
previous_url: /mobile-testing/overview
position: 0
slug: ms-overview
---

> To help you meet the demands of mobile users, Test Studio offers <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">automated responsive testing</a> enabling you to test your web application's layout, functionality and behavior on mobile and desktop browsers.
><br>
><br>
> As of March 1, 2020, native mobile testing is __no longer supported__.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

# Overview

Test Studio Mobile is an intuitive and easy to use test automation solution for Mobile application testing. Create tests once and test across multiple devices and OS.

The point and click functionality allows users to capture quickly and replay complex mobile testing functionality.  There is no need to write a single line of code.  In addition, if you like to enrich the tests with a custom logic in code, you can make use of the .NET and our mobile testing frameworks in coded test steps or standalone code files. Test against any number of real devices as you wish or through an emulator by connecting through Wifi or USB.

## Features - Test Studio Mobile desktop application.

Test Studio Mobile is a desktop application that connects your tests with targetted apps installed on remote devices. It introduces tons of fancy features that makes testing mobile apps a real pleasure: 

*	Team Collaboration: Intuitive UI with built-in IDE allow testers to craft automation and easily collaborate with SDETs and developers for long-term maintainability.

*	[Project Explorer]({% slug ms-project-explorer%}) - visualizes your tests in tree-like project structure that allows for easier navigation and management. 

*	[Test Explorer]({% slug ms-test-explorer%}) - shows open tests and the steps of the currently selected open test.

*	[Elements Explorer]({% slug ms-elements-explorer%}) - shows a tree-like view of the elements in the project. Every recorded step targets a specific element and those are elements are summarized in this view.

*	[DOM Explorer]({% slug ms-dom-explorer%}) - allows you to inspect all elements of the tested application at once, shown in a tree-like structure or in a grouped-by-tag view. Properties can be verified and steps can be added against any element in the DOM explorer.

*	[Step Builder]({% slug ms-step-builder%}) - this feature allows you to add context-based steps to your test manually. Works in a tight relation with DOM explorer.

*	[Output]({% slug ms-output-pane%}) - this pane displays a record of log messages recorded by Test Studio Mobile throughout runtime. 

*	Connected devices - view a list of all currently connected devices that are ready for test recording/execution. 

*	Results (Test Lists) - this pane displays test list results in a list-like format. 

*	Properties - this context-based pane shows properties of the currently selected item - this can be the project, test, step, element, folder, code file, connected device or a test list.

*	<a href="/features/testing-types/load-testing/configure-remote-device" target="_blank">Load testing with mobile device traffic:</a> Connect your device(s) to Test Studio’s built-in remote proxy to quickly capture scenarios for load testing.

## Features - Supported testing scenarios.

Test Studio Mobile covers a wide range of testing scenarios, including native, hybrid, web, NativeScript (Android and iOS) and Xamarin (iOS) apps testing. Tests can be recoreded or manually written and executed solely or inside test lists. 

### Platforms support

Nowadays mobile apps can be created using different platforms. Test Studio Mobile supports the most recognized and utilized of them including Android and iOS:

*	Testing Native apps - both Android and iOS native apps are supported. Just configure your [Android App]({% slug ms-configure-android%}) or [iOS app]({% slug ms-configure-ios%}) to be testable and start recording your tests.

*	Testing Hybrid apps - both Android and iOS hybrid apps are supported. Just configure your [Cordova]({% slug ms-configure-hybrid%}) or [AppBuilder (Telerik Platform)]({% slug ms-configure-hybrid-appbuilder%}) app to be testable and start recording your tests.

*	Testing Web apps - the most used mobile browsers are supported - Safari for iOS and Chrome and Firefox for Android are supported. Test Studio uses a proxy to [configure your mobile web app]({% slug ms-configure-tsm%}) for testing.

*	Testing NativeScript apps - making a NativeScript app testable is achieved by adding a separate plugin with a [single line of code]({% slug ms-configure-nativescript%}).

*	Testing Xamarin apps (iOS only) - just [configure your Xamarin Studio app]({% slug ms-configure-xamarin-ios%}) to be testable and start recording your tests.

### Connecting Agents (Devices)

Test recording and execution is performed on connected devices. Test Studio Mobile supports both physical and virtual Android and iOS devices and provides the following options for connecting them:

*	[Wi-Fi connection]({% slug ms-connect-agent-wifi%}) - connect your Android or iOS device to Test Studio Mobile over Wi-Fi. This connection type is tailored for Native or Hybrid app testing and requires installation of the Mobile Testing Agent app. 

*	[USB connection]({% slug ms-connect-agent-usb%}) - connect your Android or iOS device to Test Studio Mobile over USB cable. This connection type is tailored for Native or Hybrid app testing and requires installation of the Mobile Testing Agent app. 

*	[Web connection]({% slug ms-configure-tsm%}) - connect a browser in your Android or iOS device to Test Studio Mobile over Wi-Fi. This connection type is tailored only for Web app testing and requires redirecting web traffic through a Test Studio Mobile proxy.

### Recording and Execution

As a complete mobile app testing solution, Test Studio Mobile supports the following approaches for test recording and execution:

*	Test Studio Mobile recorder - this built in feature allows you to create your tests without writing a single line of code and supports multiple gestures such as scroll, zoom, swipe, pinch etc. In record mode any action preformed over the tested app is automatically recorded as a step in the test. Those steps can be then refined if they are not recorded correctly and can be used with [Android native]({% slug ms-record-test-android%}), [Android hybrid]({% slug ms-record-test-android-hybrid%}), [iOS native]({% slug ms-record-test-ios%}), [iOS hybrid]({% slug ms-record-test-ios-hybrid%}) and [Web]({% slug ms-record-test-web%}) tests.

*	Coded tests support - scenarios that go beyond the Test Studio Mobile Recorder capabilities can be automated with code. Coded support includes [coded steps]({% slug ms-coded-steps%}) inside any type of test and [code item]({% slug ms-code-item%}) files that are compiled separately from tests. Adding assembly references and code compilation in both C# and VB languages are supported. 

*	[Quick execution]({% slug ms-quick-execution%}) - a single test execution that provides results for the test itself and for every step in the test. Can be run on a single connected device only.

*	[Test List execution]({% slug ms-testlist-execution%}) - a single test list execution against one or more connected devices. Results are provided for the test list, every test in the test list and every step in every test.

*	[Mobile Runtime]({% slug ms-download%}#4-Mobile-Runtime) - despite Test Studio Mobile can be installed on Windows machines only, already recorded tests can be executed on Windows, Mac and Linux machines. 

## Next Steps

+ [Getting started with Native and Hybrid apps testing]({% slug ms-getting-started-native%})
+ [Getting started with Web testing]({% slug ms-getting-started-web%})

## Resources

<ul>
	<li>
		<a href="http://www.telerik.com/support/teststudio" target="_blank">Test Studio Learning and Support Resources</a>
	</li>
	<li>
		<a href="http://www.telerik.com/webinars/teststudio" target="_blank">Test Studio Webinars</a>
	</li>
</ul>