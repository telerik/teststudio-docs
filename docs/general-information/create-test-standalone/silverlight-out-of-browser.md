---
title: Silverlight Out-of-Browser
page_title: Create a Silverlight Out-of-Browser Test (Standalone)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Create a Silverlight Out-of-Browser Test (Standalone)#

__Important Notes:__


* If you are testing a Silverlight In-Browser web application, we recommend treating it as a standard <a href="web-test" target="_blank">Web Test</a> with no additional configuration.

* See <a href="http://msdn.microsoft.com/en-us/library/dd550721(v=vs.95).aspx" target="_blank">here</a> for what constitutes Out-of-Browser.

* Once a Silverlight Out-of-Browser application is configured for recording, Test Studio modifies its shortcut to point directly to the application's location on disk. This replaces the Microsoft "offline://" notation. The side effect of this is that your application will not detect that it is running in Out-of-Browser mode and code must be written in the application to work around this limitation.

* Test Studio does not support the Web Browser control in Silverlight Out-of-Browser applications.

1. <a href="/getting-started/create-test-standalone/add-test" target="_blank">Add a Web Test</a> to your test project. 

2. Click the __Out-Of-Browser__ icon in the __Silverlight__ ribbon.

	![OOB button][4]

3. Check the __Configure this test to run against a Silverlight application__ box in Out-Of-Browser options.
4. Browse for the Local Application Directory or drag and drop a link to your Silverlight application.
5. Select __Silverlight Out-of-Browser__ under __Recording Host__.

	![Recording host][5]

6. Click __Record__ to launch the out-of-browser app with the recording toolbar docked at the top.
7. Notice that steps are added to the test as actions are taken within the application.

![Recording][6]

[1]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig1.png
[2]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig2.png
[3]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig3.png
[4]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig4.png
[5]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig5.png
[6]: /img/general-information/create-test-standalone/silverlight-out-of-browser/fig6.png
