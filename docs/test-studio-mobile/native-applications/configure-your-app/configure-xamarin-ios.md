---
title: Xamarin iOS
page_title: Xamarin iOS Testing
description: Apply our testing extension to your Xamarin application.
slug: ms-configure-xamarin-ios
tags: testing, xamarin
publish: true
position: 6
---

#Configure your Xamarin iOS app to be testable

> The application configured following the steps bellow, should be used for testing purposes only and will not be accepted in Apple App Store. 

Since building Xamarin iOS mobile applications produce native iOS apps, they can be easily tested with Test Studio Mobile. [This getting-started article]({% slug ms-getting-started-native%}) provides more details about testing native iOS apps.

## Add Extension

1. [Download](/samples/MobileTestingExtension_iOS.zip) the Test Studio Mobile extension for iOS and unpack it.
2. To bring the extension into your project, select the project from the solution explorer and press **Command + Option + A** to open the `Add files` dialog. Add **libMobileTestingExtension.a** to the project. When prompted, tell Xamarin Studio to copy it into the project.

    ![Add extension xamarin ios](/img/test-studio-mobile/configure-your-app/configure-xamarin-ios/fig1.png)

## Add URL Type

1. Open the **Info.plist** file, navigate to the **Advanced** tab and add a new `URL Type`.
    *  **Identifier:** com.telerik.automation
    *  **URL Schemes:** APPLICATIONNAME
    *  **Role:** Editor

    ![Add URL](/img/test-studio-mobile/configure-your-app/configure-xamarin-ios/fig2.png)

    > The **URL Schemes** should not contain any spaces. The APPLICATIONNAME portion need not match your app name exactly. The only requirement is that APPLICATIONNAME is unique so it does not conflict with another testable application.<br/>
    If you deploy the app to an **iOS 9 device** then you must use one of the names listed bellow:
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


## Configure Xamarin.iOS to Link the Library

1. Right-click the Xamarin iOS project and choose **Options**
2. Expand **Build** and select **iOS Build**
3. At the bottom of the dialog set the following to the **Additional mtouch arguments** text field:

  `-gcc_flags "-L${ProjectDir} -force_load ${ProjectDir}/libMobileTestingExtension.a -lMobileTestingExtension -licucore -framework CFNetwork -framework Security -framework QuartzCore"`

    ![Xamarin link](/img/test-studio-mobile/configure-your-app/configure-xamarin-ios/fig3.png)

    > When targetting iOS7 you may need to add the **-all_load** flag to the **Additional mtouch arguments**:<br/><br/>
    `-gcc_flags "-L${ProjectDir} -all_load -force_load ${ProjectDir}/libMobileTestingExtension.a -lMobileTestingExtension -licucore -framework CFNetwork -framework Security -framework QuartzCore"`


    > More information about linking iOS libraries in Xamarin project is available [here](http://developer.xamarin.com/guides/ios/advanced_topics/native_interop/).

4. Close the Project Options dialog and click **Run**.

    > After the `Build Succeeded` message, you may have to wait up to 10 seconds for the application to deploy. The device's screen will be black in the meantime.

    > You may need to close your application (and the Mobile Testing Agent app) on the device before deploying.


See Also
--------

+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})