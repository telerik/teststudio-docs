---
title: Android Configuration Settings
page_title: Android Configuration Settings
description: Apply our testing extension to your native Android application.
slug: ms-configure-android-settings
tags: android testing, native
publish: true
position: 0
previous_url: /test-studio-mobile/troubleshooting-mb/configure-android-settings
---

> Although the Mobile testing module is in the process of discontinuation, Test Studio main product continues supporting <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">responsive mobile testing for web applications</a> to help meeting the demand of mobile users.

#Android Configuration Settings

Configuring an Android app to be testable is a complicated process that unzips the app (.apk) file, changes it and then rebuilds it. Several **Android** and **Java** tools are taking part into the process and that is why it is important to have all configurations correctly set. The configuration mechanism saves and loads these settings from a file that is created the first time Android application configuration is initiated. The file contents is in pure text format and can be edited manually using any text editor. However, it is not recommended to manually edit it except in the cases listed in this topic.

The first time **Android** application configuration is started, a path to the **Android SDK** and **Java JDK** folders must be set. Those values are then saved in the configuration settings file and can be changed either through the Android application configuration dialog or manually. If either of the values is not valid or does not exist, error messages are shown and configuration can't be continued. 

![SDK_JAVA_errors](/img/test-studio-mobile/troubleshooting-guide/android-configuration/fig1.png)

In some cases Android application configuration can't be continued even when **Android SDK** and **Java JDK** paths are set correctly. In addition to these 2 parameters, it also depends on Android build tools version and Android platforms installed. They are automatically set based on the Android SDK value. If for some reason the saved Android Build Tools and Platform values become invalid (e.g. uninstall them from the Android SDK Manager), Android application configuration won't work and errors will be shown. To fix this you can either:
	
1. Open the Android application configuration dialog and delete the **Android SDK** value and enter it again. This will initiate a new automatic detection of the Android build tools and Android platform versions.
	
2. Close the Android application configuration dialog. Edit the values manually in the configuration file that is by default located in `%USERPROFILE%\AppData\Roaming\ArtOfTest\MtAPKProvisioningSettings.json`. 

![BuildTool_Platform](/img/test-studio-mobile/troubleshooting-guide/android-configuration/fig2.png)

After the configuration file is edited, save it and reopen Android application configuration dialog to pick the new values.