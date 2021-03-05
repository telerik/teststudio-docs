---
title: Web Test
page_title: Create and Record a Web Test (VS plugin)
description: "Test Studio Create and Record a Web Test (VS plugin) in Visual Studio Plugin"
position: 1
---
# Create and Record a Web Test (VS plugin) #

The Test Studio project in Visual Studio uses the Visual Studio context and therefore some of the main actions have different look.

In this article you can find how to add and record a new web test in the Visual Studio plugin project for Test Studio.

## Create a Web Test

1. Launch Visual Studio and create a Test Studio project from the _Start Page_.

2. Click __Telerik > Test Studio > Create New Test Project__.

 	<table id=no-table>
		<tr>
			<td>![Create project][1] <br><br>**Visual Studio 2017**</td>
			<td>![Create project VS 2019][11]<br><br>**Visual Studio 2019**</td>
		</tr>
	<table>

3. Choose __Telerik > Test > VB or C# Test Studio Project__, name the project, and click __OK__.
<br> 

 	<table id=no-table>
		<tr>
			<td>![Choose C#/VB project][2]<br><br>**Visual Studio 2017**</td>
			<td>![Choose C#/VB project VS 2019][12]<br><br>**Visual Studio 2019**</td>
		</tr>
	<table>

4. By default the newly created project contains a Web test.

	![Web Test by deafault](/img/general-information/create-test-vsplugin/web-test/web-test-by-default.png)

5. To add new tests in the project, click with the right mouse button on the project name in _Solution Explorer_, select _Add_ and choose between _Test Studio Web Test..._ or _Test Studio WPF Test..._.

	![Add new test](/img/general-information/create-test-vsplugin/web-test/add-new-test.png)

The respective item is selected in the list of items, type a name and click _Add_. To open the test, double click on its name in the Solution Explorer.

	![Open new test](/img/general-information/create-test-vsplugin/web-test/open-new-test.png)

## Record a Web Test

1. Click the ___Record___ button to start the recording process.

	![Record][3]

	Enter the automated page URL in the popped up dialog and select the recording browser. Then click the __Record__ button to launch the recording browser session.

	![Select url and browser](/img/general-information/create-test-vsplugin/web-test/enter-url.png)

	The latest URLs used for recording will be listed in the ___Recent URLs___ section and you can select directly any of them.

2. The recording browser will start and navigate to the selected URL. Once the URL is fully loaded the __Test Studio Recorder Toolbar__ will be attached to the browser and you can continue performing the steps of the auomation scenario.

	![Browser with attached recorder][6]

3. Each action against the page will be automatically recorded and presented by a single step in the test.

	![Perform actions](/img/general-information/create-test-vsplugin/web-test/recorded-steps.png)

	To __stop the recording__ session close the browser.

[1]: /img/general-information/create-test-vsplugin/web-test/fig1.png
[2]: /img/general-information/create-test-vsplugin/web-test/fig2.png
[3]: /img/general-information/create-test-vsplugin/web-test/fig3.png
[4]: /img/general-information/create-test-vsplugin/web-test/fig4.png
[5]: /img/general-information/create-test-vsplugin/web-test/fig5.png
[6]: /img/general-information/create-test-vsplugin/web-test/fig6.png
[7]: /img/general-information/create-test-vsplugin/web-test/fig7.png
[11]: /img/general-information/create-test-vsplugin/wpf-test/fig11.png
[12]: /img/general-information/create-test-vsplugin/wpf-test/fig12.png