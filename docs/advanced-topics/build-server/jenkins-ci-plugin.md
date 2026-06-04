---
title: Jenkins CI Plugin
page_title: Jenkins CI Plugin
description: "Test Studio plugin for Jenkins Continuous integration setup. Configure the Test Studio plugin for Jenkins CI."
position: 5
---
# Test Studio Plugin for Jenkins CI

The Test Studio Plugin for Jenkins allows you to build and execute <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests and test lists in Jenkins CI environment and easily explore the generated JUnit xml results in the built-in Jenkins functionality.

>The Test Studio Plugin could be used with Test Studio projects only. If you will need to **build a Visual Studio project** or a solution use the instructions listed <a href="/advanced-topics/build-server/jenkins-ci#Build-a-Visual-Studio-project-or-a-Solution" target="_blank">**here**</a>.

1. **Install the Jenkins CI** to run as a Java application (instead of running as a Widnows service) and run the Jenkins Listener on a custom port - configure a different, non-conflicting port number for the listener (avoid port numbers 8009, 8010, 8011, 8012 and 8013 which are used by the Test Studio Scheduling Service).

2. **Install the Test Studio Plugin** - download it <a href="/downloads/Jenkins_Plugin_Teststudio.zip" target="_blank">here</a> and add it to the Plugin folder of the Jenkins server installation.

3. **Create a freestyle project**. Create an item and select 'Build a freestyle project'.

![Freestyle project](/img/advanced-topics/build-server/jenkins-ci-plugin/fig2.png)

4. **Add a Test Studio runner configuration build step**. Under the 'Add build step menu' section select 'Test Studio runner configuration'.

![TS Plugin build step](/img/advanced-topics/build-server/jenkins-ci-plugin/fig3.png)

5. **Input the full path to ArtOfTest.Runner.exe**. The default path to find the Test Runner executable is C:\Program Files (x86)\Progress\Test Studio\Bin.

6. **Specify the test or test list to execute** using the absolute path to the file in the Jenkins CI workspace or its relative path according that same workspace.

The *project root folder* and *settings file* fields accept relative path to the Jenkins job workspace only.

![Build step arguments](/img/advanced-topics/build-server/jenkins-ci-plugin/fig4.png)

7. **Choose whether to convert test or test steps to JUnit test**. By enabling the checkbox a test list will be converted as a test suite and each including test will be converted to a JUnit test in the generated JUnit xml result file. Otherwise if disabling the checkbox each test will be converted to a test suite and each of its steps will be converted to a JUnit test in the generated JUnit xml result.

![Convert to JUnit](/img/advanced-topics/build-server/jenkins-ci-plugin/fig5.png)

Your test execution step is now ready to save and run.



