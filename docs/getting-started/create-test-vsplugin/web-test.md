---
title: Web Test
page_title: Create and Record a Web Test (VS plugin)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/create-a-test-vs-plugin/web-test.aspx, /user-guide/create-a-test-vs-plugin/web-test
position: 1
---
# Create and Record a Web Test (VS plugin) #

## Create a new test ##

1.Launch Visual Studio.
2.Click __Telerik > Test Studio > Create New Test Project__.

<table id=no-table>
	<tr>
		<td>![Create project][1] <br><br>**Visual Studio 2017**</td>
		<td>![Create project VS 2019][11]<br><br>**Visual Studio 2019**</td>
	</tr>
<table>

3.Choose __Telerik > Test > VB or C# Test Studio Project__, name the project, and click __OK__.<br> 

> **Note:** As of version 2015.3.1202 Test Studio projects will appear only under **.NET Framework 4.5** or higher.

<table id=no-table>
	<tr>
		<td>![Choose C#/VB project][2]<br><br>**Visual Studio 2017**</td>
		<td>![Choose C#/VB project VS 2019][12]<br><br>**Visual Studio 2019**</td>
	</tr>
<table>

4.By default the newly created project contains a Web test.

![Web Test by deafault](/img/getting-started/create-test-vsplugin/web-test/web-test-by-default.png)

5.To add new test in the project click with the right mouse button on the project name in Solution Explorer, select Add and choose between Test Studio Web Test... or Test Studio WPF Test....

![Add new test](/img/getting-started/create-test-vsplugin/web-test/add-new-test.png)

The respective item is selected in the list of items, type a name and click Add. To open the test double click on its name in the Solution Explorer.

![Open new test](/img/getting-started/create-test-vsplugin/web-test/open-new-test.png)

## Begin Recording in the VS Plugin ##

1.Click the _Record_ button to start the recording process.

![Record][3]

In the dialog that pops up enter the URL to record a test against and select the recording browser. Then click on __Record__ button.

![Select url and browser](/img/getting-started/create-test-vsplugin/web-test/enter-url.png)

The URLs recently used for recording will be listed in the Recent URLs section where you can select directly any of them.

2.The recording browser will start and navigate to the selected URL. Once the URL is fully loaded the Test Studio Dev Recorder Toolbar will be attached to the browser and you can start performing the desired scenario.

![Browser with attached recorder][6]

3.Each action against the page will be automatically recorded and presented by a single step in the test.

![Perform actions](/img/getting-started/create-test-vsplugin/web-test/recorded-steps.png)

To stop the recording session close the browser.

[1]: /img/getting-started/create-test-vsplugin/web-test/fig1.png
[2]: /img/getting-started/create-test-vsplugin/web-test/fig2.png
[3]: /img/getting-started/create-test-vsplugin/web-test/fig3.png
[4]: /img/getting-started/create-test-vsplugin/web-test/fig4.png
[5]: /img/getting-started/create-test-vsplugin/web-test/fig5.png
[6]: /img/getting-started/create-test-vsplugin/web-test/fig6.png
[7]: /img/getting-started/create-test-vsplugin/web-test/fig7.png
[11]: /img/getting-started/create-test-vsplugin/wpf-test/fig11.png
[12]: /img/getting-started/create-test-vsplugin/wpf-test/fig12.png