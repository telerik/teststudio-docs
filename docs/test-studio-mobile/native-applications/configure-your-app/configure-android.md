---
title: Android
page_title: Configure Android App
description: Apply our testing extension to your native Android application.
slug: ms-configure-android
tags: android testing, native
publish: true
previous_url: /test-studio-mobile/configure-your-app/configure-android
position: 1
---
# Configure your Android app to be testable

> The application configured following the steps below, should be used for testing purposes only and will not be accepted in Google Play Store. 

Android apps must be configured in order to be testable by Test Studio Mobile. This can be achieved through the built-in configuration or manually:

*   [Built-In Configuration](#built-in-configuration)
*   [Manual Configuration](#manual-configuration)

## Built-In Configuration

 > The built-in configuration requires that you have Java SDK v.1.8 or later, Android SDK v.14 or later Android Build Tools v.20 or later installed (Android Build Tools are a component of the Android Studio installation).</br>

 > It doesn't change already instrumented app and you have to ensure that the `libs` folder of your project doesn't contain `MobileTestingExtension.jar` or `MobileTestingExtension.aar` files. In addition built-in configuration is not supported for the below cases:
 > * Apps downloaded from Google play or built in production mode.
 > * The app to be instrumented has more than 65536 methods and is installed on device running API level 20 and below. See [that article]({% slug ms-known-issues%}#instumentation-exception) for more information.

 The automatic configuration is incorporated into Test Studio Mobile project and can be launched by clicking the Android gear box icon at the right corner of the toolbar:

![AndroidGear](/img/test-studio-mobile/configure-your-app/configure-android/fig11.png)

The Android application configuration dialog shows up. The first-time setup requires that paths to **Android SDK** and **Java JDK** foolders are set:

![SDK_JAVA_errors](/img/test-studio-mobile/configure-your-app/configure-android/fig12.png)

 > For more informational about Android application configuration settings, please see [this article]({% slug ms-configure-android-settings%}).

After valid paths are set, the **Next** button is enabled and the **Input location** step can be selected. It allows configuring an app either already installed on a device, or taken from the local machine file system. Configuring an app installed on a device, requires that the device is **USB connected** to the local machine running Test Studio Mobile:

![InputLocation](/img/test-studio-mobile/configure-your-app/configure-android/fig13.png)

Selecting a connected device automatically loads a subset of all apps installed on it. Apps that have identifiers starting with `com.android` and `com.google` are not shown initially. In order to show all available apps on the device, check the **Show All** checkbox. In addition instead of scrolling through the list, a search box allows you to look for a specific app identifier:

![InputLocationApps](/img/test-studio-mobile/configure-your-app/configure-android/fig14.png)

 > Configuring system apps is not supported. If system app is selected the configuration will either fail or the app may become unstable. Test Studio is not responsible for any damage that a configured system app may cause.

After app to be configured is selected, the Output location step is enabled and can be navigated by clicking the **Next** button:

![OutputLocation](/img/test-studio-mobile/configure-your-app/configure-android/fig15.png)

Output location can be either the local machine file system or any of the USB connected devices:

![OuptuLocationSelection](/img/test-studio-mobile/configure-your-app/configure-android/fig16.png)

Clicking the **Run** button will start the configuration process. After the app is successfully configured it will be deployed to the selected device or saved at the specified file location.

![ProvisionedSuccessfully](/img/test-studio-mobile/configure-your-app/configure-android/fig17.png)

Testing the configured app can start immediatelly by opening an Android test and selecting a device for recording. The app identifier is automatically added and can be chosen from the list of app identifiers that is shown when recording starts. [This article]({% slug ms-record-test-android%}) describes test recording in detail.

## Manual Configuration

> The manual configuration requires the source code (Android Studio/Eclipse project).

Configure your Android app to be testable.

* [Android Studio and AAR extension](#android-studio-and-aar-extension)
* [Android Studio and JAR extension](#android-studio-and-jar-extension)
* [Eclipse](#eclipse)

# Android Studio and AAR extension.

## Copy Extension

1. [Download](/samples/MobileTestingExtension_Android.zip) the Test Studio Mobile extension for Android and unpack it.
2. Open `/MobileTestingExtension_Android/`.
3. Copy `MobileTestingExtension.aar`.
4. In your project open `/projectFolder/mymodulename/libs`.
5. Paste `MobileTestingExtension.aar`.

## Configure Module gradle settings

1. Open `/projectFolder/mymodulename/build.gradle`.
2. Add the following `productFlavors` in the `android` object:

        productFlavors {
            myFlavor {
                targetSdkVersion 0
            }
        }

3. Add the following line to the `dependencies` section:

        myFlavorCompile (name: 'MobileTestingExtension', ext: 'aar')
        
    ![Manual Aar Module](/img/test-studio-mobile/configure-your-app/configure-android/fig18.png)

## Configure Project gradle settings

1. Open `/projectFolder/build.gradle`.
2. Add the following `flatDir` element in the `repositories` object:
        
        flatDir {
            dirs 'libs'
        }
        
    ![Manual Aar Project](/img/test-studio-mobile/configure-your-app/configure-android/fig19.png)

3. Sync the project and select **View > Tool Windows > Build Variants**.
4. Select the **myFlavorDebug** build variant and deploy it.

    ![Build Flavour](/img/test-studio-mobile/configure-your-app/configure-android/fig20.png)


<a href="#Configure-your-Android-app-to-be-testable">Back to Top</a>
<br><br>

# Android Studio and JAR extension.

## Copy Extension

1. [Download](/samples/MobileTestingExtension_Android.zip) the Test Studio Mobile extension for Android and unpack it.
2. Open `/MobileTestingExtension_Android/`.
3. Copy `MobileTestingExtension.jar`.
4. In your project open `/projectFolder/mymodulename/libs`.
5. Paste `MobileTestingExtension.jar`.

## Add Flavors

1. Open your project in Android Studio.
2. Right Click on the project and select **Open Module Settings**.
3. Click **app** under **Project Settings**.
4. Click the **Flavors** tab.
5. Click **+** to add two new entries: `production` and `mobileTesting`.

    ![Product Flavors](/img/test-studio-mobile/configure-your-app/configure-android/fig1.png)

6. Click **OK**.

## Configure Testing Flavor

1. Open `/projectFolder/mymodulename/build.gradle`.
2. Add the following after `productFlavors` in the `android` object:

        android.applicationVariants.all { variant ->
        if (variant.flavorName == 'mobileTesting') {
            variant.outputs[0].processResources.manifestFile = file("src/${variant.flavorName}/AndroidManifest.xml")
            variant.outputs[0].processManifest.enabled=false
            }
        }

![Build Variants](/img/test-studio-mobile/configure-your-app/configure-android/fig3.png)

## Include Extension

1. Open `/projectFolder/mymodulename/build.gradle`.
2. Add the following lines to the `dependencies` section:

        mobileTestingCompile files('libs/MobileTestingExtension.jar')
        
    ![Apply Testing Extension in Android Studio](/img/test-studio-mobile/configure-your-app/configure-android/fig4.png)

## Create Subfolders

Create the following subfolders in the project:

* `/projectFolder/mymodulename/src/mobileTesting`

## Copy Android Manifest

1. Open `/projectFolder/mymodulename/src/main`.
2. Copy `AndroidManifest.xml`.
3. Open `/projectFolder/mymodulename/src/mobileTesting`.
4. Paste `AndroidManifest.xml`.

## Edit Android Manifest

1. Open `/projectFolder/mymodulename/src/mobileTesting/AndroidManifest.xml`.
2. Verify that the permisiion element **android.permission.SYSTEM_ALERT_WINDOW** is added to the manifest file. 
3. Add the following top-level `instrumentation` element which will be used as App-Identifier in Test Studio Mobile (don't forget to change `your.app.package` with your actuall app package name):

        <instrumentation
            android:targetPackage="your.app.package"
            android:name="com.telerik.testingextension.MobileTestingInstrumentation" />

    ![Instrumentation](/img/test-studio-mobile/configure-your-app/configure-android/fig5.png)

4. Add the following `activity` element as a child of the `application` element:

        <activity
            android:name="com.telerik.testingextension.EntryPoint"
            android:theme="@android:style/Theme.NoDisplay">
        <intent-filter>
            <action android:name="com.telerik.testing.ACTION_AUTOMATE"/>
            <category android:name="android.intent.category.DEFAULT"/>
        </intent-filter>
        </activity>

    ![Activity](/img/test-studio-mobile/configure-your-app/configure-android/fig6.png)

5. Select **View > Tool Windows > Build Variants**.
6. Select the **mobileTestingDebug** build variant and deploy it.

    ![Testing Build Variant](/img/test-studio-mobile/configure-your-app/configure-android/fig7.png)

<a href="#Configure-your-Android-app-to-be-testable">Back to Top</a>
<br><br>

# Eclipse
## Copy Extension

1. Open `/Telerik Mobile Testing/extensions/Android`.
2. Copy `MobileTestingExtension.jar`.
3. Open `/projectFolder/libs`.
4. Paste `MobileTestingExtension.jar`.

![Add Extension](/img/test-studio-mobile/configure-your-app/configure-android/fig8.png)
## Edit Android Manifest

1. Open `/projectFolder/AndroidManifest.xml`.
2. Verify that the permisiion element **android.permission.SYSTEM_ALERT_WINDOW** is added to the manifest file. 
3. Add the following top-level `instrumentation` element which will be used as App-Identifier in Test Studio Mobile:

        <instrumentation
            android:targetPackage="your.app.package"
            android:name="com.telerik.testingextension.MobileTestingInstrumentation" />

    ![Instrumentation Eclipse](/img/test-studio-mobile/configure-your-app/configure-android/fig9.png)

4. Add the following `activity` element as a child of the `application` element:

        <activity
            android:name="com.telerik.testingextension.EntryPoint"
            android:theme="@android:style/Theme.NoDisplay">
        <intent-filter>
            <action android:name="com.telerik.testing.ACTION_AUTOMATE"/>
            <category android:name="android.intent.category.DEFAULT"/>
        </intent-filter>
        </activity>

    ![Activity Eclipse](/img/test-studio-mobile/configure-your-app/configure-android/fig10.png)

5. Build the project and deploy it.

<a href="#Configure-your-Android-app-to-be-testable">Back to Top</a>
<br><br>

See Also
--------

+ [Record Android Test]({% slug ms-record-test-android%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})