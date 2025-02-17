---
title: Test Settings for Test Explorer
page_title: Test Settings for Test Explorer
description: Test Settings for Test Explorer. Apply Test Studio specific settings for the test runs from Visual Studio Test Explorer. 
position: 5
---
# Test Explorer Settings

Running a Test Studio test from the Test Explorer in Visual Studio uses a set of default settings. To control the options for the test run, you need a test settings file which Visual Studio project recognizes.

This article describes the details for this settings file and how to use it for the Test Studio test runs initiated from the Visual Studio Test Explorer.

- [Test Explorer Settings](#test-explorer-settings)
  - [Visual Studio 2019 and 2022](#visual-studio-2019-and-2022)


> __Note!__
><br>
><br>
> The _runsettings_ file for the Visual Studio Test Explorer affects only individual tests runs. <a href="/automated-tests/vs-plugin/test-lists-in-vs-2017-2019#test-list-settings-in-visual-studio" target="_blank">Test List settings</a> are controlled for each test list individually.

## Visual Studio 2019 and 2022

To specify the settings for the Test Studio test runs from the Test Explorer you need to choose a _RunSettings_ file in the Visual Studio project.

__1.&nbsp;__ You can download a zipped _runsettings_ file from <a href="/teststudio/demoslibrary/TestSettings1.zip" target="_blank">here</a> and unzip it in a folder.

__2.&nbsp;__ To change any setting open the _runsettings_ file in a text editor app (like Notepad++) and modify the settings to customize the test run from Test Explorer.

__3.&nbsp;__ To use these Test Studio specific settings for the test runs initiated from the Test Explorer, you need to configure the file to be used as run settings in the project.

![Set run settings for Test Explorer 2019 and 2022](/img/knowledge-base/visual-studio-kb/test-explorer-settings/run-settings-vs22.png)

__4.&nbsp;__ You can store the file in the project root folder and use the option __Auto Detect runsettings Files__. The alternative is to specify the file from an external location through the __Select Solution Wide runsettings File__.


[1]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig1.png
[2]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig2.png
[3]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig3.png
[4]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig4.png