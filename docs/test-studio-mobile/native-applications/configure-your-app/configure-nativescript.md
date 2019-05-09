---
title: NativeScript
page_title: Configure NativeScript App
description: Apply our testing extension to your NativeScript application.
slug: ms-configure-nativescript
tags: NativeScript, native, script
publish: true
previous_url: /test-studio-mobile/configure-your-app/configure-nativescript
position: 3
---

#Configure your NativeScript app to be testable.

> The application configured following the steps below, should be used for testing purposes only and will not be accepted in Apple App Store and Google Play Store. 

Since building NativeScript mobile applications produce native iOS and Android apps, they can be easily tested with Test Studio Mobile. [This getting-started article]({% slug ms-getting-started-native%}) provides more details about testing native iOS and Android apps.

1. The first step is to prepare the NativeScript application.

 > If you don't have NativeScript installed you can follow [this intallation guide](https://docs.nativescript.org/start/quick-setup)

	If you don't have a NativeScript application to configure, you can create a new one by executing the following command:

		tns create myApplicationName


	Android

	![Create Android](/img/test-studio-mobile/configure-your-app/configure-nativescript/CreateProject-Android.png)

	iOS

	![Create iOS](/img/test-studio-mobile/configure-your-app/configure-nativescript/CreateProject-iOS.png)

2. Next you need change the current folder to the newly created app folder and add the Test Studio Mobile plugin for NativeScript with the following command:

		tns plugin add nativescript-teststudio


	Android

	![AddPlugin Android](/img/test-studio-mobile/configure-your-app/configure-nativescript/AddPlugin-Android.png)

	iOS

	![AddPlugin iOS](/img/test-studio-mobile/configure-your-app/configure-nativescript/AddPlugin-iOS.png)

	During execution of the command the specific app id is set that Test Studio Mobile will use to start the app:

	* For the Android version of the application, the **"id"** key that is set when the project is created is used. This key can be found in application's *package.json* file. :

			...
		 	"nativescript": {
	    		"id": "org.nativescript.justTest",
		    	...
		    	}, 
			...

	* For the iOS version of the application, **"telerikmt1"** is set by default and used as URL Scheme required to access the tested application. For more information please read the note for URL Schemes in this [article]({% slug ms-configure-ios%}#Add-URL-Type)

	If you want to add the plugin and set the iOS parameter value with a single command, you can use the extended version of *tns* command as follows:

		tns plugin add nativescript-teststudio --var.IOS_APP_URL iosAppUrl

	Here you need to replace *iosAppUrl* with the value you want your app to use.

	> The Android parameter can't be changed with the CLI command. However both Android and iOS parameters can be changed manually in the *package.json* file.
	
	To confirm that you've correctly changed the app iOS url, you can check the *package.json* of the NativeScript application. The new value is added to the *"nativescript-teststudio-variables"* key. You can change this value in order to access the application from Test Studio with different url.

		"nativescript-teststudio-variables": {
		      "IOS_APP_URL": "telerikmt1"
	    	}

3. The next step is to prepare, build and deploy the application to a device or an emulator (you may need to have the device/emulator started):
	
	Android

		tns run android

	![RunProject Android](/img/test-studio-mobile/configure-your-app/configure-nativescript/RunProject-Android.png)

	iOS

		tns run ios

	![RunProject iOS](/img/test-studio-mobile/configure-your-app/configure-nativescript/RunProject-iOS.png)


4. Now you can begin to test the UI with Test Studio as described in this [article]({% slug ms-create-test%}).


> If you don't want to use the NativeScript plugin as described above, you can setup the generated native project manually. Open the project for each platform (from *platforms/ios* or *platforms/android*) and follow the steps required for configuring native [iOS]({% slug ms-configure-ios%}) and [Android]({% slug ms-configure-android%}#Manual) applications. 

> You can configure native Android applications automatically right from within the Mobile Test Studio. Read more [here]({% slug ms-configure-android%}#Built-In-Configuration).


See Also
--------

+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Record Android Test]({% slug ms-record-test-android%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})