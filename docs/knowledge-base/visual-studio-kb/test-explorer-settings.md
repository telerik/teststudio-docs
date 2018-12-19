---
title: Test Explorer Settings
page_title: Test Explorer Settings
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Test Explorer Settings#

*If a project is exported to Visual Studio - settings from Test Studio project are not applied when executing tests from Test Explorer*

##Solution##

To apply the missing settings it will be necessary to add a test settings file for the Visual Studio project and set it to be used by the Test Explorer. 

1.&nbsp; Right click on the solution and choose Add -> New Item...

![Add new item][1]

2.&nbsp; Then choose **Test Settings** and click the **Add** button

![Test settings item][2]

3.&nbsp; The new settings file will appear in the solution explorer. Once you open it, select the **Telerik Test Studio** tab to find the project settings in format similar to the one in Test Studio and modify these accordingly.

![Settings][3]

4.&nbsp; To apply these settings file for the Test Explorer execution select the newly created settings file from *Test -> Test Settings -> Select Test Settings File*.

![Assign to Test Explorer][4]


[1]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig1.png
[2]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig2.png
[3]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig3.png
[4]: /img/knowledge-base/visual-studio-kb/test-explorer-settings/fig4.png