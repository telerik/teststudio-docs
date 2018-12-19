---
title: Jenkins Plugin Mobile Runner
page_title: Jenkins Plugin Mobile Runner
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
# Mobile Test Studio Plugin for Jenkins CI #

The Test Studio Plugin allows you to build and execute Mobile Test Studio tests and test lists in Jenkins CI environment and easily explore the generated JUnit xml results in the built-in Jenkins functionality.

1.&nbsp; **Install the Mobile Studio Plugin** - download it <a href="/downloads/Jenkins_Plugin_Mobilestudio.zip" target="_blank">here</a> and add it to the Plugin folder of the Jenkins server installation.

2.&nbsp; **Create a freestyle project**. Create an item and select 'Build a freestyle project'.

![Freestyle project][2]

3.&nbsp; **Add a Mobile Studio Runner configuration build step**. Under the 'Add build step menu' section select 'Mobile Studio runner configuration'.

![TS Plugin build step][3]

4.&nbsp; **Input the full path to Telerik.MobileTesting.Runner.exe**. The default path to find the Test Runner executable is C:\Program Files (x86)\Progress\Test Studio\Bin\MobileStudio.

5.&nbsp; **Input Message Server address** - running <a href="/test-studio-mobile/features/message-server" target="_blank">message server</a> to which the devices are connected to.

6.&nbsp; **Input device ID** to execute the tests on. 

7.&nbsp; **Specify the test or test list to execute** using full or relative path to the file and the project root folder full path.

![Build step arguments][4]

8.&nbsp; **Choose whether to represent test or test steps as a JUnit test**. By enabling the checkbox a *test list* will be represented as a test suite and each including test will be represented as a JUnit test. 

![Convert to JUnit][5]

9.&nbsp; **Add post build action** - to publish JUnit test results report. This will provide results to be visible from Jenkins UI.

![Publish in JUnit][6]

Your test execution step is now ready to save and run.

[1]: /img/advanced-topics/build-server/jenkins-ci-plugin/fig1.png
[2]: /img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/jenkins-plugin/fig2.png
[3]: /img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/jenkins-plugin/fig3.png
[4]: /img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/jenkins-plugin/fig4.png
[5]: /img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/jenkins-plugin/fig5.png
[6]: /img/test-studio-mobile/knowledge-base-tm/continuous-integration-tm/jenkins-plugin/fig6.png

