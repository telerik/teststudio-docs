---
title: Xamarin Android
page_title: Xamarin Android Testing
description: Apply our testing extension to your Xamarin application.
slug: ms-configure-xamarin-android
tags: testing, xamarin
publish: true
position: 6
---

#Configure your Xamarin Android app to be testable

## Prerequsites:

* Visual Studio 2015 or 2017 with installed "Modile development with .NET" workload

![New install][1]

* Test Studio Mobile Android extension:
    1. [Download](http://docs.telerik.com/teststudio/samples/MobileTestingExtension_Android.zip) the Test Studio Mobile extension for Android and unpack it
    2. Extract MobileTestingExtension.jar somewhere on your PC

## Building the Xamarin bindings library:

1.&nbsp; Start new Visual Studio project and select Templates->Android->Bindings Library (Android)

![New Binding Library][2]

2.&nbsp; Add **MobileTestingExtension.jar** to project:

```
    Solution Explorer->Right click on 'Jars' folder->Add->Existing Item...    
    Navigate to MobileTestingExtension.jar and add it to the project.
```

![Adding JAR to project][3]

3.&nbsp; Edit **MobileTestingExtension.jar** properties:

```
    In Solution Explorer select MobileTestingExtension.jar and change 'Build Action' to 'EmbeddedJar'
```

![Configuring JAR][4]

4.&nbsp; Open project Properties and set **Target Framework** to be same as **Target Framework** of the application that will be tested.

![Properties][5]

5.&nbsp; Ensure to set explicitly the **Android Codegen Target** in project Properties to *jar2xml*.

![Codegen Target][6]


6.&nbsp; Build Bindings library. You probably will get some warning messages in output console, but the library should be build sucefully and ouputed DLL will be located at:

```
Visual Studio Projects\ClassLibrary\ClassLibrary\bin\Debug\ClassLibrary.dll
```

For more information about building Xamarin bindings library see: [Creating Bindings Library](https://developer.xamarin.com/guides/android/advanced_topics/binding-a-java-library/binding-a-jar/#Creating_the_Bindings_Library)


## Configuring Xamarin application:

1.&nbsp; Add Bindings Library to the project under test:

![References][7]

2.&nbsp; Open **AndroidManifest.xml** for editing

![AndroidManifest][8]

3.&nbsp; Add the following top-level instrumentation element which will be used as App-Identifier in Test Studio Mobile and change target package name to match your application package:

```
 <instrumentation
        android:name="com.telerik.testingextension.MobileTestingInstrumentation"
        android:targetPackage="Todo.Android"/>
```

![Instrumentation][9]

4.&nbsp; Add the following activity element as a child of the application element:

```
<activity android:name="com.telerik.testingextension.EntryPoint"
        android:theme="@android:style/Theme.NoDisplay" >
    <intent-filter>
    <action android:name="com.telerik.testing.ACTION_AUTOMATE"/>
    <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>
```

![Activity][10]

5.&nbsp; Your application is ready for testing.

For more information about recording and executing tests with Test Studio Mobile see: [Test Studio Mobile Help](http://docs.telerik.com/teststudio/test-studio-mobile/overview)

[1]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/new-install.png
[2]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/new-bindings-library.png
[3]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/add-jars.png
[4]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/configure-jar.png
[5]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/properties.png
[6]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/codegen-target.png
[7]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/references.png
[8]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/AndroidManifest.png
[9]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/instrumentation.png
[10]: /img/test-studio-mobile/configure-your-app/configure-xamarin-android/activity.png
