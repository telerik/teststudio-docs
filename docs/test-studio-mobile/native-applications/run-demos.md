---
title: Run Demos
page_title: Run Demos
description: How to build, deploy and run the demo applications
previous_url: /test-studio-mobile/installation/run-demos,/test-studio-mobile/native-applications/installation/run-demos
position: 3
slug: ms-run-demos
---
#Run Demo Applications

* <a href="#Android-Demo-App">Android Demo App</a>
* <a href="#iOS-Demo-App">iOS Demo App</a>
* <a href="#Hybrid-Demo-App">Hybrid Demo App</a>

##Android Demo App

1. [Install]({% slug ms-install-agent-app%}) the Mobile Testing Agent app to a physical or virtual device.

2. [Download](/samples/androidDemoApplication.zip) Android demo application and unzip it.

3. Open **Android Studio**

4. Select **Open an existing Android Studio Project**

5. Open /DemoApplication and click **OK**

	![Open demo application](/img/test-studio-mobile/install/run-demos/fig1.png)

6. Select **View > Tool Windows > Build Variants**

7. Select the **mobileTestingDebug** build variant

	![Select testing debug](/img/test-studio-mobile/install/run-demos/fig2.png)

8. Click **Run** to deploy the demo app to a device or an emulator.

	![Run the demo app](/img/test-studio-mobile/install/run-demos/fig3.png)

9. After the demo app is deployed, you can [record Android test]({% slug ms-record-test-android%}) and [execute it]({% slug ms-quick-execution%}). Alternatively download the [mobile demo tests project](/samples/DemoMobileProject.zip), open it in Test Studio Mobile and excute tests in `Android_Native_Tests` folder.

##iOS Demo App

1. [Install]({% slug ms-install-agent-app%}) the Mobile Testing Agent app to a physical or virtual device.

2. [Download](/samples/xCodeDemoApplication.zip) iOS demo application and unzip it. 

3. Open **Xcode**

4. Select **File > Open**

5. Open /DemoApplication/DemoApplication.xcodeproj and click **Open**.

	![Open demo application](/img/test-studio-mobile/install/run-demos/fig4.png)

6. Select the **DemoApplicationQA** target and select a device or simulator

7. Click **Run**

	![Run the demo app](/img/test-studio-mobile/install/run-demos/fig5.png)

8. After the demo app is deployed, you can [record iOS test]({% slug ms-record-test-ios%}) and [execute it]({% slug ms-quick-execution%}). Alternatively download the [mobile demo tests project](/samples/DemoMobileProject.zip), open it in Test Studio Mobile and excute tests in `iOS_Native_Tests` folder.

## Hybrid Demo App

1. [Install]({% slug ms-install-agent-app%}) the Mobile Testing Agent app to a physical or virtual device.

2. [Download](/samples/cordovaDemoApplication.zip) Hybrid (Cordova) demo application and unzip it. 

3. Open a command window in the `DemoApplication` folder and follow the [Cordova Command-line Interface][1] guide to add required platforms and deploy to devices or emulators.

4. After the demo app is deployed, you can record [Android Hybrid test]({% slug ms-record-test-android-hybrid%}) or [iOS Hybrid test]({% slug ms-record-test-ios-hybrid%}) and [execute it]({% slug ms-quick-execution%}). Alternatively download the [mobile demo tests project](/samples/DemoMobileProject.zip), open it in Test Studio Mobile and excute the Android Hybrid tests in the `Android_Hybrid_Tests` folder or the iOS Hybrid tests in the `iOS_Hybrid_Tests` folder.

See Also
--------

+ [Agent App Installation]({% slug ms-install-agent-app%})
+ [Downloads]({% slug ms-download%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Record iOS Hybrid Test]({% slug ms-record-test-ios-hybrid%})
+ [Record Android Test]({% slug ms-record-test-android%})
+ [Record Android Hybrid Test]({% slug ms-record-test-android-hybrid%})

[1]: https://cordova.apache.org/docs/en/latest/guide/cli/index.html