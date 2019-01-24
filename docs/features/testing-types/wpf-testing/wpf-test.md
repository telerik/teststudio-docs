---
title: Configure WPF Test
page_title: Configure WPF Test (Standalone)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /getting-started/create-test-standalone/wpf-test
position: 1
---
# Configure a WPF Test #

After <a href="/getting-started/create-test-standalone/add-test" target="_blank">adding</a> a WPF test, you need to configure it for the application you intend to record tests against.

![Configure][3]

## Configure WPF Test to Record the Specific Application ##

1. Click the ***Configure*** button in the *Test* ribbon.

![Configure][3]

1. The __Configure WPF Application Path__ window appears. There are two options to determine the default application to launch when recording and executing this test.
	* __WPF Application Path__ - drag and drop the shortcut icon into this text box, or click __Browse__ and locate it manually.
	* __Current Path Expanded__ - read-only display of full path if environment variables are used.
	* __Use default path__ - whether to use the path set here or the default path set in __Project Settings > General__.
	* __Active WPF Applications__ - Progress Test Studio detects all WPF apps currently running and lists them. Highlight the desired app and press __Select Application__.
	* __Recording Options__ - set the default behavior whether to record window state changes.

![Configure][4]

	* Click __OK__. If you need to later modify the WPF application path, choose __Configure__ from the toolbar.
	* Hit __Record__ to launch the app with the recording toolbar docked at its bottom.

![Record][5]

Notice that steps are added to the test as actions are taken within the application.
	

[1]: /img/getting-started/create-test-standalone/wpf-test/fig1.png
[2]: /img/getting-started/create-test-standalone/wpf-test/fig2.png
[3]: /img/getting-started/create-test-standalone/wpf-test/fig3.png
[4]: /img/getting-started/create-test-standalone/wpf-test/fig4.png
[5]: /img/getting-started/create-test-standalone/wpf-test/fig5.png