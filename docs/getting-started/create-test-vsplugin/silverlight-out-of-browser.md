---
title: Silverlight Out-of-Browser
page_title: Create a Silverlight Out-of-Browser Test (VS plugin)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Create a Silverlight Out-of-Browser Test (VS plugin) #

__Important Notes:__


* If you are testing a Silverlight In-Browser web application, we recommend treating it as a standard <a href="web-test" target="_blank">Web Test</a> with no additional configuration.

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

[1]: /img/getting-started/create-test-vsplugin/silverlight-out-of-browser/fig1.png
[2]: /img/getting-started/create-test-vsplugin/silverlight-out-of-browser/fig2.png
[3]: /img/getting-started/create-test-vsplugin/silverlight-out-of-browser/fig3.png
[4]: /img/getting-started/create-test-vsplugin/silverlight-out-of-browser/fig4.png
[5]: /img/getting-started/create-test-vsplugin/silverlight-out-of-browser/fig5.png
