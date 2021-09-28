---
title: Silverlight Out-of-Browser
page_title: Create a Silverlight Out-of-Browser Test (VS plugin)
description: "Test Studio Create a Silverlight Out-of-Browser Test (VS plugin)"
position: 3
---
# Create a Silverlight Out-of-Browser Test (VS plugin) #

Test Studio supports Silverlight Out-of-Browser applications and below you can read how to create a test for that type of app.

> __Important!__
><br>
><br>
> As of Test Studio release __R3 2020 SP1 (v.2020.3.1209)__ Silverlight Out-of-Browser testing in Test Studio is no longer visible in the main Test Studio user interface. If you want to continue using it, see <a href="#enable-silverlight-out-of-browser-in-test-studio-2020-r3-sp-release">here</a> how to enable it.

__Important Notes:__

* If you are testing a Silverlight In-Browser web application, we recommend treating it as a standard <a href="/automated-tests/recording/overview" target="_blank">Web Test</a> with no additional configuration.

* See <a href="http://msdn.microsoft.com/en-us/library/dd550721(v=vs.95).aspx" target="_blank">here</a> for what constitutes Out-of-Browser.

* Once a Silverlight Out-of-Browser application is configured for recording, Test Studio modifies its shortcut to point directly to the application's location on disk. This replaces the Microsoft "offline://" notation. The side effect of this is that your application will not detect that it is running in Out-of-Browser mode and code must be written in the application to work around this limitation.

* Test Studio does not support the Web Browser control in Silverlight Out-of-Browser applications.

1. Launch Test Studio.
2. Click __Telerik > Test Studio > Create New Test Project__.

	![Create test project][1]

3. Choose __Telerik > Test > VB or C# Test Studio Project__, name the project, and click __OK__.<br> 

	**Note:** As of version 2015.3.1202 Test Studio projects will appear only under **.NET Framework 4.5** or higher.

	![Create C#/VB project][2]


4. A Web Test is added to the project. Open it and click the __Configure Silverlight App__ icon in the toolbar.

	![Configure SL App][3]

5. Check the __Configure this test to run against a Silverlight application__ box in Out-Of-Browser options.
6. Browse for the Local Application Directory or drag and drop a link to your Silverlight application.
7. Select __Silverlight Out-of-Browser__ under __Recording Host__.

	![Recording host][4]

8. Click __Record__ to launch the out-of-browser app with the recording toolbar docked at the top.

![Recording test][5]

Notice that steps are added to the test as actions are taken within the application.

## Enable Silverlight Out-Of-Browser in Test Studio 2020 R3 SP Release

The icon to configure a test for __Silverlight-Out-Of-Browser__ application testing is __removed in Test Studio release R3 SP 2020 (v.2020.3.1209)__. You still can bring up the icon back in the product.

Open the Windows Registry Editor and navigate to key _HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Telerik\TestStudio_. Add a new string type key named _ShowSilverlightOutOfBrowser_ and set its value to _true_. Restart Test Studio and the Silverlight-Out-Of-Browser icon will appear back in the _test options_.

[1]: /img/general-information/create-test-vsplugin/silverlight-out-of-browser/fig1.png
[2]: /img/general-information/create-test-vsplugin/silverlight-out-of-browser/fig2.png
[3]: /img/general-information/create-test-vsplugin/silverlight-out-of-browser/fig3.png
[4]: /img/general-information/create-test-vsplugin/silverlight-out-of-browser/fig4.png
[5]: /img/general-information/create-test-vsplugin/silverlight-out-of-browser/fig5.png
