---
title: iOS
page_title: Configure iOS App
description: Apply our testing extension to the QA target of your native iOS application.
slug: ms-configure-ios
tags: ios testing, native
publish: true
previous_url: /test-studio-mobile/configure-your-app/configure-ios
position: 2
---

#Configure your iOS app to be testable

> The application configured following the steps bellow, should be used for testing purposes only and will not be accepted in Apple App Store. 

## Duplicate Target

1. Open your project in Xcode. This guide uses the open source application Wikipedia as an example.
2. Select the project file in Xcode in order to view the list of Targets.

    ![List of Targets](/img/test-studio-mobile/getting-started-mb/configure-ios/wikipedia-mobile.png)

3. Right click the target for testing and click **Duplicate**.

    ![Creating the Duplicate Target](/img/test-studio-mobile/getting-started-mb/configure-ios/wikipedia-mobile-copy.png)

4. Rename the new target to `ApplicationNameQA`.

  > This signifies that the target is a QA-only build, and should not be used as a release.

5.  Since Xcode does not do it automatically, update the new target’s associated files, settings, and schemes to reflect the new target name.

  > Update the build settings to properly reference any property list files you rename.

  ![The Renamed Target](/img/test-studio-mobile/getting-started-mb/configure-ios/wikipedia-mobile-qa.png)
    
  This table contains the items to update when a target is duplicated:

   <table>
    <tbody>
      <tr>
        <td><strong>Target</strong></td>
        <td>ApplicationName copy &gt; ApplicationNameQA</td>
      </tr>
      <tr>
        <td><strong>Target .plist file</strong></td>
        <td>ApplicationName copy-Info.plist &gt; ApplicationNameQA.plist</td>
      </tr>
      <tr>
        <td><strong>Target &gt; Build Settings &gt; Packaging &gt; Info.plist File</strong></td>
        <td>ApplicationName copy-Info.plist &gt; ApplicationNameQA.plist</td>
      </tr>
      <tr>
        <td><strong>Target &gt; Build Settings &gt; Packaging &gt; Product Name</strong></td>
        <td>ApplicationName copy &gt; ApplicationNameQA</td>
      </tr>
      <tr>
        <td><strong>Scheme &gt; Manage Schemes</strong></td>
        <td>ApplicationName copy &gt; ApplicationNameQA</td>
      </tr>
    </tbody>
  </table>

  > If you're using the Wikipedia app as an example and intend to deploy it to your device, modify the following setting to build it with your own credentials: **Target &gt; Summary &gt; iOS Application Target &gt; Bundle Identifier**.

  ![The Modified Bundle Indentifier](/img/test-studio-mobile/getting-started-mb/configure-ios/bundle-identifier.png)

## Add Extension

1. Select the new target in the **Scheme** drop-down.
2. [Download](/samples/MobileTestingExtension_iOS.zip) the Test Studio Mobile extension for iOS and unpack it.
3. Open `/MobileTestingExtension_iOS/` and drag **libMobileTestingExtension.a** into your Project's file listing.

    ![Dragging the Static Library](/img/test-studio-mobile/getting-started-mb/configure-ios/drag-static-lib-new.png)
	
	>If you target to automate [WKWebView's](https://developer.apple.com/library/ios/documentation/WebKit/Reference/WKWebView_Ref/)  in your project, drag **libMobileTestingWebKit.a** into your Project's file listing as well.

4. Select **Create folder references for any added folders**.
5. Uncheck the original target and check the new QA target.
6. Click **Finish**.

    ![Linking the Static Libraries](/img/test-studio-mobile/getting-started-mb/configure-ios/adding-plugin-options.png)

7. Go to **Build Phases &gt; Link Binary With Libraries**. A reference to the testing extension is automatically added. Add **libicucore.tbd**, **Security.framework**,  **QuartzCore.framework** and **CFNetwork.framework** if they are not already linked. In older versions of Xcode you may need to add **libicucore.dylib** instead of **libicucore.tbd**. This grants WebSocket compatibiltiy.
    
    > If you target to automate WKWebView's in your project, **WebKit.framework** must also be added.

    ![The Successfully Linked Static Library](/img/test-studio-mobile/getting-started-mb/configure-ios/linked-lib-new.png)

8. Go to **Build Settings &gt; Linking** and add `-add_load` to **Other Linker Flags**.

    ![Other Linker Flags](/img/test-studio-mobile/getting-started-mb/configure-ios/other-linker-flags-2.png)

    > This ensures all symbols from the static libraries compile correctly into the target application.

## Add URL Type

1. Go to the **Info** tab of the `QA` target's settings and click **+** to add a new URL Type.

  *  **Identifier:** com.telerik.automation
  *  **URL Schemes:** APPLICATIONNAME
  *  **Role:** Editor

  ![Adding the URL Type](/img/test-studio-mobile/getting-started-mb/configure-ios/adding-the-url-type-3.png)

  > The **URL Schemes** should not contain any spaces. The APPLICATIONNAME portion need not match your duplicate Target name exactly, however we recommend consistency. The only requirement is that APPLICATIONNAME is unique so it does not conflict with another testable application.

  > If you deploy the app to an **iOS 9+** device  then you must use one of the names listed bellow:
  *	telerikmt1
  *	telerikmt2
  *	telerikmt3
  *	telerikmt4
  *	telerikmt5
  *	telerikmt6
  *	telerikmt7
  *	telerikmt8
  *	telerikmt9
  *	telerikmt10
  *	tsdemoapplication

2. Select the newly configured target and click **Run**.

  > After the `Build Succeeded` message, you may have to wait up to 10 seconds for the application to deploy. The device's screen will be black in the meantime.

  > You may need to close your application (and the {{site.mt}} app) on the device before deploying.


## Application ID

The Application Identifier is setup during the instrumentation process of the testable app. The Application Identifier is combination of URL Schemes suffixed with **://**.

> When used in Test Studio Mobile, the `Application Identifier` must be suffixed with **://**. For example, the app identifier that is setup in previous section is **WikipediamobileQA** (no trailing colon and slashes), but suffixed with **://** when entered in the Test Studio Mobile **Set Application ID** dialog.

![APPID](/img/test-studio-mobile/getting-started-mb/configure-ios/appID.png)

##iOS 9 Confirmation Dialogs

iOS 9 introduces a feature that requires user confirmation when Mobile Testing Agent app starts an app under test. As a result a confirmation dialog is shown the first time tests are run and after the first test is executed. Once Open is chosen for both dialogs they won't be presented any more. However the first execution may still fail because of the interruption caused by the dialogs.

<table id="no-table">
	<tr>
		<td>![Conformation dialog 1](/img/test-studio-mobile/getting-started-mb/configure-ios/confdialog1.png)</td>
		<td>![Conformation dialog 2](/img/test-studio-mobile/getting-started-mb/configure-ios/confdialog2.png)</td>
	</tr>
<table>


See Also
--------

+ [Record iOS Test]({% slug ms-record-test-ios%})
+ [Playback Tests]({% slug ms-quick-execution%})
+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})