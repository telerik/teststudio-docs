---
title: Continious Integration Overview
page_title: Telerik Testing in Continuous Integration Environments
description: "Telerik Testing in Continuous Integration Environments with Test Studio"
previous_url: /user-guide/command-line-test-execution/continuous-integration/continuous-integration-environments.aspx, /user-guide/command-line-test-execution/continuous-integration/continuous-integration-environments
position: 1
---
# Telerik Testing in Continuous Integration Environments #

Continuous Integration almost continuously integrates the individual developer's changes into the main source code control system or repository, performing a new build, verifying the build, and running automated tests against those builds. Continuous integration has many advantages. These include the constant availability of a current build for testing purposes, immediate testing of all changes, and the opportunity for developers to revert the codebase back to a bug-free state when a test fails or a bug is discovered, without wasting time debugging. Learn more about continuous integration at <a href="http://msdn.microsoft.com/en-us/library/ee308011(v=vs.100).aspx" target="_blank">MSDN</a> and Martin Fowler's <a href="http://www.martinfowler.com/articles/continuousIntegration.html" target="_blank">Continuous Integration</a>.

Continuous integration environments use a variety of build tools, including <a href="http://msdn.microsoft.com/en-us/library/0k6kkbsd.aspx" target="_blank">MSBuild</a>. Automation of the build can include deployment into a testing environment that closely mimics production. The build can include the project to be tested, as well as Telerik Testing Framework tests and coded steps of Test Studio tests.

Once the build completes, tests may run automatically. The build automation can use <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner</a> or <a href="/features/test-runners/mstest" target="_blank">MSTest</a> to execute Telerik tests against the build. As part of the automated build process, Telerik test results can publish to custom locations. ArtOfTest.Runner publishes test results as .aiiresults files; MSTest publishes results as .trx files.

Because the framework actually drives and interacts with the browser, the setup of the testing agents is sensitive. Many automated build servers and testing agents run under the 'Local System' or 'Local Service' account. This will cause Telerik tests to fail, because browser interaction is prohibited for these types of accounts.

The testing agent (sometimes identical with the build server) must run in console mode (that is, started via the command line after logging onto the testing machine). Running a testing agent as a service that logs onto a real user account does not provide full functionality. Some Telerik test features require desktop interaction, which is disabled for test agents running as a service.
Do not run Telerik tests in parallel. Telerik tests are not thread safe. Also, if one Telerik test is running at the time a second test opens, the second test may connect to the browser window already connected to the first Telerik testing session. 

## Setup automated testing agents ##

1. Log onto the testing agent machine using an account with permissions needed to run your agent and unit tests.

2. Install your testing agent software.

3. Run the testing agent in console mode (from the command line or a shortcut link). Do not run the agent as a service.

4. Install Test Studio or the Telerik Testing Framework. Enter your license.

5. Leave the machine running and logged into the account. If your tests perform direct desktop interaction (such as Desktop.Mouse.Click or Window.GetBitmap), do not lock the machine. Instead, leave your machine logged on and displaying the desktop at all times. Disable the screensaver and **never lock** the machine.

## Examples of Implementing Test Studio tests in Different CI Tools

* <a href="/advanced-topics/build-server/azure-devops" target="_blank">Azure DevOps</a>
* <a href="/advanced-topics/build-server/jenkins-ci" target="_blank">Jenkins CI</a>
* <a href="/advanced-topics/build-server/team-city-builds" target="_blank">TeamCity</a>
* <a href="/advanced-topics/build-server/bamboo" target="_blank">Bamboo</a>
* <a href="/advanced-topics/build-server/cruise-control.net-builds" target="_blank">CruiseControl .Net</a>
