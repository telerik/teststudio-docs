---
title: Test Explorer Settings
page_title: Test Explorer Settings - Test Studio Dev Documentation
description: Settings to apply to Test Studio Dev tests when executing from Test Explorer
position: 1
---
# Test Explorer Settings

Running a __Test Studio Dev__ test from the Test Explorer in Visual Studio uses a set of default settings. To control the options for the test run, you need a test settings file recognized from the Visual Studio project.

This article describes the details for this settings file and how to use it for the Test Studio test runs initiated from the Visual Studio Test Explorer.

* [Add Test Explorer runsettings file in Test Studio Dev project in Visual Studio 2019 and 2022](#visual-studio-2019-and-2022)
* [Add Test Explorer testsettings file in Test Studio Dev project in Visual Studio 2017](#visual-studio-2017)

> __Note!__
><br>
><br>
> The _runsettings_ file for the Visual Studio Test Explorer affects only individual tests runs. <a href="/features/test-execution/test-lists-in-vs-2017-2019#test-list-settings-in-visual-studio" target="_blank">Test List settings</a> are controlled for each test list individually.

## Visual Studio 2019 and 2022

To specify the settings for the Test Studio test runs from the Test Explorer you need to choose a _RunSettings_ file in the Visual Studio project.

__1.&nbsp;__ You can download a zipped _runsettings_ file from <a href="/downloads/TestSettings1.zip" target="_blank">here</a> and unzip it in a folder.

__2.&nbsp;__ To change any setting open the _runsettings_ file in a text editor app (like Notepad++) and modify the settings to customize the test run from Test Explorer.

__3.&nbsp;__ To use these Test Studio specific settings for the test runs initiated from the Test Explorer, you need to configure the file to be used as run settings in the project.

![Set run settings for Test Explorer 2019 and 2022](images/test-explorer-settings/run-settings-vs22.png)

__4.&nbsp;__ You can store the file in the project root folder and use the option __Auto Detect runsettings Files__. The alternative is to specify the file from an external location through the __Select Solution Wide runsettings File__.

## Visual Studio 2017

To specify the settings for the Test Studio test runs from the Test Explorer you need to create a _testsettings_ file in the Visual Studio project.

__1.&nbsp;__ Right click on the solution name in the __Solution Explorer__ and choose the option __Add -> New Item...__

![Add new item][1]

__2.&nbsp;__ Then choose the **Test Settings** option, enter specific name for the settings file and click the **Add** button.

![Test settings item][2]

__3.&nbsp;__ This new settings file appears in the __Solution Explorer__ under the __Solution Items__ section. Double click the file to open it and choose the last section **Telerik Test Studio** on the left side list. The Test Studio specific settings are listed on the right side of the pane under three tabs - __General__, __Web__ and __WPF__, and are accessible to modify these and customize the test runs.

![Settings][3]

__4.&nbsp;__ Select _testsettings_ file under __Test -> Test Settings -> Select Test Settings File__.

![Set test settings for Test Explorer 2017][4]

[1]: images/test-explorer-settings/fig1.png
[2]: images/test-explorer-settings/fig2.png
[3]: images/test-explorer-settings/fig3.png
[4]: images/test-explorer-settings/fig4.png