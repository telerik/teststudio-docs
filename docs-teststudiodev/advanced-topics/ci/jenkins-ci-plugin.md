---
title: Jenkins CI Plugin
page_title: Jenkins CI Plugin | Test Studio Dev Documentation
description: Test Studio Dev Plugin for Jenkins CI
position: 2
---
# Test Studio Plugin for Jenkins CI

The Test Studio Plugin allows you to build and execute Test Studio tests and test lists in Jenkins CI environment and easily explore the generated JUnit xml results in the built-in Jenkins functionality.

>The Test Studio Plugin supports Test Studio projects only.

1.Install the Jenkins CI server to run as a Java application (instead of running it as a Windows service).

2.Install the Test Studio Plugin - download it <a href="/downloads/Jenkins_Plugin_TeststudioDev.zip" target="_blank">here</a> and add it to the Plugin folder of the Jenkins server installation or download it from the jenkins plugin marketplace.

3.Create a freestyle project. Create an item and select 'Build a freestyle project'.

![Freestyle project][2]

4.Add a Test Studio runner configuration build step. Under the 'Add build step menu' section select 'Test Studio runner configuration'.

![TS Plugin build step][3]

5.Input the full path to ArtOfTest.Runner.exe. The default path to find the Test Runner executable is C:\Program Files (x86)\Progress\Test Studio\Bin.

6.Specify the test or test list to execute using the absolute path to the file in the Jenkins CI workspace or its relative to the workspace path.

The *project root folder* and *settings file* fields accept relative path to the Jenkins job workspace only.

![Build step arguments][4]

7.TestStudio test as junit test. If enabled, in the test result, test studio tests will be represented as junit tests. Otherwise, test steps from the test studio result will be represented as junit tests.

![Convert to JUnit][5]

Your test execution step is now ready to save and run.

[1]: images/ciplugin/fig1.png
[2]: images/ciplugin/fig2.png
[3]: images/ciplugin/fig3.png
[4]: images/ciplugin/fig4.png
[5]: images/ciplugin/fig5.png