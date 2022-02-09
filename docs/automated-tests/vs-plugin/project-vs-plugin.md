---
title: Create Test Studio Project
page_title: Create Test Studio Project in Visual Studio Plugin
description: "Create Test Studio Project in Visual Studio Plugin. Get familiar with the Test Studio components in Visual Studio Project. Where to find the Step Builder and Elements Explorer in the Visual Studio Plugin project."
position: 0
---
# Create Test Studio Project in Visual Studio Plugin

The Test Studio project in Visual Studio uses the Visual Studio context so some of its components may have different look and feel.

In this article you can find details for the Test Studio specific features and where to find them in the Visual Studio project.

## Create a Project in Visual Studio

Launch Visual Studio and choose the option to __Create a new project__.

![VS Create new project](/img/automated-tests/vs-plugin/create-project/vs-start-screen.png)

This option guide you to a list with all available project templates depending on the installed Visual Studio components. Enter _'Test Studio'_ in the search field to filter the list. You can see there are two type of project templates - one is C# project and the other is VisualBasic. Choose the one, which suits you best and click __Next__ button.

![Choose Project template](/img/automated-tests/vs-plugin/create-project/filter-project-types.png)

On the next screen you can change some of the project initial configuration like its name, folder location, solution name and targeted .Net framework version (the <a href="/system-requirements#net-framework-requirement" target="_blank">minimum requirement</a> is v.4.5.2).
Use the __Create__ button to get the new project created.

![Name the Project](/img/automated-tests/vs-plugin/create-project/project-config.png)

The Test Studio project in Visual Studio is now launched. The project template loads with an empty web test in it.

![New project in VS](/img/automated-tests/vs-plugin/create-project/new-project-created.png)

### Create a New Project from Running Visual Studio

You can create a new Test Studio project from the _Telerik_ menu available in Visual Studio toolbar.

In __Visual Studio 2015 and 2017__ the _Telerik_ menu is listed as separate one and you can find the option under __Telerik -> Test Studio -> Create New Test Project__

In __Visual Studio 2019 and later__ the _Telerik_ menu is listed under the _Extensions_ menu and you can find the option under __Extensions -> Telerik -> Test Studio -> Create New Test Project__

<table id=no-table>
	<tr>
		<td>![Create project][1] <br><br>**Visual Studio 2015 and 2017**</td>
		<td>![Create project VS 2019][11]<br><br>**Visual Studio 2019 and Later**</td>
	</tr>
<table>

## Test Studio Components in the Visual Studio Project

In the context of Visual Studio you have access to the Test Studio specific components like the <a href="/automated-tests/elements/overview" target="_blank">Elements Explorer</a>, <a href="/features/project-settings/overview" target="_blank">Project Settings</a> and the <a href="/features/custom-steps/overview" target="_blank">Step Builder</a>. These panes will not be visible by default in the Visual Studio instance. You can toggle the panes to be visible from the specific Test Studio toolbar options and place these where suitable for you in the project area.

![New project in VS](/img/automated-tests/vs-plugin/create-project/test-studio-specific-panes.png)

> __Tip__
><br>
><br>
> The Elements Explorer and Step Builder panes can be also toggled from the _Telerik_ menu __Extensions -> Telerik -> Test Studio -> Show Elements Explorer/Show Step Builder__.

## Test Studio Tests Specific Options

All options specific for the Test Studio test context are listed in the toolbar of an open test.

![New project in VS](/img/automated-tests/vs-plugin/create-project/test-studio-test-specific-options.png)

In this toolbar you can find the following features:

- The <a href="/automated-tests/vs-plugin/web-test" target="_blank">__Record__ and __Execute__ buttons</a>. 
- The <a href="/automated-tests/vs-plugin/wpf-test" target="_blank">__Configure options__ for the WPF test</a>.
- The <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">__Visual Debugger__ options</a>.
- The <a href="/automated-tests/test-execution/quick-run-timeouts" target="_blank">__quick run timeout__ options</a>.
- The <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">option to __add external data source__</a>.
- The <a href="/automated-tests/vs-plugin/convert-steps-code" target="_blank">options to __convert the test into coded one__</a>.
- The <a href="/features/test-maintenance/test-step-properties" target="_blank">specific from Test Studio perspective __test properties__</a>.

## Next Steps

The below topics cover the basic specifics of the Test Studio project in Visual Studio context.

* <a href="/automated-tests/vs-plugin/web-test" target="_blank">Create and record a web test</a>
* <a href="/automated-tests/vs-plugin/wpf-test" target="_blank">Create and record a WPF test</a>
* <a href="/automated-tests/vs-plugin/test-lists-in-vs-2017-2019" target="_blank">Create and run test list in Visual Studio project</a>
* <a href="/automated-tests/vs-plugin/vs-test-explorer" target="_blank">Execute Test Studio tests from the Test Explorer in Visual Studio</a>
* <a href="/automated-tests/vs-plugin/test-explorer-settings" target="_blank">Apply Test Studio specific settings for the Test Explorer execution</a>
* <a href="/automated-tests/vs-plugin/test-results-vs" target="_blank">Explore the results of the different test runs</a>
* <a href="/automated-tests/vs-plugin/convert-steps-code" target="_blank">Coding options in Visual Studio</a>
