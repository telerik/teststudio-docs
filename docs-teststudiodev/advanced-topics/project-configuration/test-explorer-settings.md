---
title: Test Explorer Settings
page_title: Test Explorer Settings - Test Studio Dev Documentation
description: Settings to apply to Test Studio Dev tests when executing from Test Explorer
position: 1
---
# Test Explorer Settings

Running a __Test Studio Dev__ test from the Test Explorer in Visual Studio uses a set of default settings. To control the options for the test run, you need a test settings file recognized from the Visual Studio project.

This article describes how to create such file and use it for the Test Studio Dev test execution from the Visual Studio Test Explorer.

* [Add Test Explorer settings file in Test Studio Dev project in Visual Studio 2022](#visual-studio-2022)
* [Add Test Explorer settings file in Test Studio Dev project in Visual Studio 2019 and earlier](#visual-studio-2019-and-earlier)
* [Configure Test Explorer to use the test settings file](#configure-test-explorer-to-use-the-test-studio-specific-settings)

## Add a Test Settings File in Visual Studio Project

The Test Studio Dev specific settings are accessible through a specific test settings file in the Visual Studio project.

### Visual Studio 2022

Visual Studio 2022 deprecates the test settings type of file and it cannot be created for a Test Studio Dev project opened in this version. Though, it still can be __used in the VS 2022 project__, if you have an existing test settings file.

__1.&nbsp;__ You can download a zipped test settings file from <a href="/downloads/TestSettings1.zip" target="_blank">here</a> and unzip it in a folder.

__2.&nbsp;__ Right click on the solution name in the __Solution Explorer__ and choose the option __Add -> Existing Item...__. Select the test settings file from the location you downloaded and unzipped it and confirm the selection with pressing the __Add__ button.

![Add Existing Item](images/test-explorer-settings/add-existing-item.png)

__3.&nbsp;__ This newly added settings file appears in the __Solution Explorer__ under the __Solution Items__ section. Double click the file to open it and choose the last section **Telerik Test Studio** on the left side list. The Test Studio Dev specific settings are listed on the right side of the pane under three tabs - __General__, __Web__ and __WPF__, and are accessible to modify these and customize the test runs.

![Settings](images/test-explorer-settings/fig3.png)

> __Note!__
><br>
><br>
> Due to the specifics of Visual Studio projects, the file is not actually included in the project folder. If you want to keep it within the project, you can use the __Save As...__ option to save the file in the project folder.

### Visual Studio 2019 and Earlier

For __Visual Studio 2015, 2017 and 2019__ projects you can add such file out-of-the-box following the below steps:

__1.&nbsp;__ Right click on the solution in the __Solution Explorer__ and choose the option __Add -> New Item...__

![Add new item][1]

__2.&nbsp;__ Then choose the **Test Settings** option, enter specific name for the settings file and click the **Add** button.

![Test settings item][2]

__3.&nbsp;__ This new settings file will appear in the __Solution Explorer__ under the __Solution Items__ section. Double click the file to open it and choose the last section **Telerik Test Studio** on the left side list. The Test Studio Dev specific settings are listed on the right side of the pane under three tabs - __General__, __Web__ and __WPF__, and are accessible to modify these and customize the test runs.

![Settings][3]

## Configure Test Explorer to Use the Test Studio Specific Settings

To use these Test Studio Dev specific settings for the test runs initiated from the Test Explorer, you need to set the test settings file to be used as run settings.

In __Visual Studio 2015 and 2017__ the test settings can be set under __Test -> Test Settings -> Select Test Settings File__.

In __Visual Studio 2019 and 2022__ the test settings file can be selected under __Test -> Configure Run Settings -> Choose Solution Wide runsettings File__

<table id="no-table">
<tr>
<td>![Set test settings for Test Explorer 2015 and 2017][4]<br>__Visual Studio 2015 and 2017__</td>
<td>![Set run settings for Test Explorer 2019 and 2022](images/test-explorer-settings/run-settings-vs22.png)<br>__Visual Studio 2019 and 2022__</td>
<tr>
<table>

[1]: images/test-explorer-settings/fig1.png
[2]: images/test-explorer-settings/fig2.png
[3]: images/test-explorer-settings/fig3.png
[4]: images/test-explorer-settings/fig4.png