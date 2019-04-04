---
title: WPF Test
page_title: Create and Record a Wpf Test (VS plugin)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/create-a-test-vs-plugin/wpf-test.aspx, /user-guide/create-a-test-vs-plugin/wpf-test
position: 2
---
# Create and Record a WPF Test (VS plugin) #

1. Launch Test Studio.
2. Click __Telerik > Test Studio > Create New Test Project__.

<table id=no-table>
	<tr>
		<td>![Create project][1] <br><br>**Visual Studio 2017**</td>
		<td>![Create project VS 2019][11]<br><br>**Visual Studio 2019**</td>
	</tr>
<table>

3. Choose __Telerik > Test > VB or C# Test Studio Project__, name the project, and click __OK__.

**Note:** As of version 2015.3.1202 Test Studio projects will appear only under **.NET Framework 4.5** or higher.

<table id=no-table>
	<tr>
		<td>![Choose C#/VB project][2]<br><br>**Visual Studio 2017**</td>
		<td>![Choose C#/VB project VS 2019][12]<br><br>**Visual Studio 2019**</td>
	</tr>
<table>

4. Right click on the project node in the solution explorer and select __Add > New WPF Test__.

![New WPF test][3]

5. Click __Add__.

![Add][4]

6. Open the new test and click the __Configure WPF Application Path__ icon in the toolbar.

![Configure path][5]

7. The __Configure WPF Application Path__ window appears. There are two options to determine the default application to launch when recording and executing this test.
	
	*	__WPF Application Path__ - drag and drop the shortcut icon into this text box, or click __Browse__ and locate it manually.
	*	__Current Path Expanded__ - read-only display of full path if environment variables are used.
	*	__Use default path__ - whether to use the path set here or the default path set in __Project Settings > General__.
	*	__Active WPF Applications__ - Progress Test Studio detects all WPF apps currently running and lists them. Highlight the desired app and press __Select Application__.
	*	__Recording Options__ - whether to record window state changes.

8. Hit __Record__ to launch the app with the recording toolbar docked at the top.
9. Notice that steps are added to the test as actions are taken within the application.

![Record][6]

10.Close the application to stop recording.


[1]: /img/getting-started/create-test-vsplugin/wpf-test/fig1.png
[2]: /img/getting-started/create-test-vsplugin/wpf-test/fig2.png
[3]: /img/getting-started/create-test-vsplugin/wpf-test/fig3.png
[4]: /img/getting-started/create-test-vsplugin/wpf-test/fig4.png
[5]: /img/getting-started/create-test-vsplugin/wpf-test/fig5.png
[6]: /img/getting-started/create-test-vsplugin/wpf-test/fig6.png
[7]: /img/getting-started/create-test-vsplugin/wpf-test/fig7.png
[11]: /img/getting-started/create-test-vsplugin/wpf-test/fig11.png
[12]: /img/getting-started/create-test-vsplugin/wpf-test/fig12.png