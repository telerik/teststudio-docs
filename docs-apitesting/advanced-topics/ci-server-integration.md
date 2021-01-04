---
title: CI Server Integration
page_title: CI Server Integration
description: "Progress® Test Studio® for APIs - CI Server Integration"
previous_url: /api-testing/advanced-topics
position: 1
publish: true
---

# CI Server Integration

Continuous Integration regularly integrates the individual developer's changes into the main source code control system or repository, performing a new build, verifying the build, and running automated tests against those builds. Continuous integration has many advantages. These include the constant availability of a current build for testing purposes, immediate testing of all changes, and the opportunity for developers to revert the codebase back to a bug-free state when a test fails or a bug is discovered, without wasting time debugging. Learn more about continuous integration at <a href="http://msdn.microsoft.com/en-us/library/ee308011(v=vs.100).aspx">MSDN</a> and Martin Fowler's <a href="http://www.martinfowler.com/articles/continuousIntegration.html">Continuous Integration</a>.

Thanks to its command line interface, Test Studio for APIs can easily be integrated in most famous CI Servers.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

## Jenkins Integration
 
 * Install Progress® Test Studio® for APIs on your Jenkins slave or master machine (where you will execute your Jenkins project)
   * You can alternatively just copy the Telerik.ApiTesting.Runner.exe with the whole "runnerconsole" directory as described [here](/features/command-line/overview). 
 * Configure the test execution command (see [Command Line Parameters](/features/command-line/command-line-parameters)
 ) - we recommend saving it to a build.cmd file. This is an example:
 
 `Telerik.ApiTesting.Runner.exe test -p "demotests" -f junit -v base-url=http://localhost:5000 -o testresult.xml`
 
 * Execute the build.cmd file as a build step from the Jenkins project
 * Publish JUnit test results report

    ![Publish JUnit](/img/advanced-topics/ci-server-integration/publish-junit.png)

 * As of release **R1 2018 (v. 2018.1.301)** you could alternatively use the Api Testing Jenkins Plugin. Please see below for more details.

## Jenkins Plugin

 * Download the plugin from [here](/downloads/Jenkins_Plugin_Apitesting.zip) and add it to the Plugin folder of the Jenkins server installation.
 * Create an item and select 'Build a freestyle project'. Under the 'Add build step menu' section select 'Test Studio for API runner configuration'.

 ![Build Step API Runner Configuration](/img/advanced-topics/ci-server-integration/build-api-runner-task.png)

 * **Input the full path to the Telerik.ApiTesting.Runner.exe**. The default path to find the Test Runner executable is C:\Program Files (x86)\Progress\Test Studio\Bin\ApiTesting\runnerconsole.
 * **Specify the project root folder** using full or relative path.
 * **Specify the test/tests to execute** using relative path(s) to the test file(s) (relative to the project root folder).
 * Optionally, you could execute specific steps within a test case by specifying "Start from" and/or "Stop after" keys, or you can set variables for the test run. 
 * **Choose whether to convert test or test steps to JUnit test**. By default, a test case in Test Studio for APIs will be converted in the test results as a "test suite" and test steps will appear as "test cases" in order to provide lower granularity of results. If you check the "Test as junit test" option, test suites in Test Studio for APIs will appear as "test suites" in the junit results, and test cases will appear accordingly as "test cases". 

![Build step options](/img/advanced-topics/ci-server-integration/build-task-options.png)

## Other CI Servers

> Coming soon ...
