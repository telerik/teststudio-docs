---
title: TFS Builds
page_title: TFS Builds
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/command-line-test-execution/continuous-integration/team-foundation-server-builds.aspx, /user-guide/command-line-test-execution/continuous-integration/team-foundation-server-builds
position: 2
---
#Telerik Testing Framework and Team Foundation Server Builds#

##Introduction##

If you use the default settings to run Telerik tests as part of your TFS build, they will fail. This is because the TFS build agent runs as a service and services are not allowed desktop interaction as required by Telerik tests.

##Getting the build agent to successfully run Telerik tests##

Team Foundation Server performs builds on build agents. After you install and configure TFS you need to install the build agent on at least one machine. The install for TFS does not automatically install the build agent.
 
You can install the build agent on the same machine as your Team Foundation Server or a different machine. Generally it is better to use a separate machine for your build agent so that builds do not take up resources needed by the server thereby causing server performance degradation. However, if your Team Foundation Server is very lightly loaded, it is OK to install the build agent onto the same machine.
 
In order for the build agent machine to run unit tests it needs to have the following software installed in addition to the build agent that comes with TFS:

* Visual Studio Team System for Testers or Visual Studio Team System for Developers.

* Telerik Testing Framework.
 
Your unit tests need access to the Visual Studio and ArtOfTest testing frameworks on the build agent machine.
 
In order for Telerik tests to successfully run they need to be able to interact with the desktop. In order for them to do that the build agent needs to be run in interactive (i.e. console) mode. Unfortunately the install of the build agent automatically installs the agent as a windows service and starts it. This is easily changed by following the procedure at <a href="http://msdn.microsoft.com/en-us/library/vstudio/ms181712(v=vs.110).aspx#interactive" target="_blank">http://msdn.microsoft.com/en-us/library/vstudio/ms181712(v=vs.110).aspx#interactive</a>.
 
This prevents the agent from automatically running as a service and runs it from the command line instead. Be sure to leave the computer logged on and the TFSBuildService window open. Your build agent is running in that window. If you close that window or logoff the computer, the build agent will stop and you won't get any builds or unit tests run.
 
Most Telerik tests work just fine if you leave the computer locked (displaying the logon screen) so long as the build agent is running under a user account with desktop interaction privileges (which all regular users have). The only tests that may have a problem with this are those that interact directly with the desktop (Mouse.Click, Window.GetBitmap, etc.). Tests that exclusively interact directly with the Browsers DOM will run just fine this way. Unfortunately there's no way around this. This is simply the way that Windows works.
 
In order for Telerik tests that interact directly with the desktop to work you'll need to leave your TFS build agent machine logged on and displaying the desktop all the time. This means you'll have to disable the screensaver and never lock the computer. Yes, this presents a security risk to your company. If you can lock this computer up into a secure room (such as a datacenter), you can minimize this security risk.

##Specifying what tests to run##

In TFS 2010/2012, continuous integration is accomplished through <a href="http://msdn.microsoft.com/en-us/library/gg413265(v=vs.100).aspx" target="_blank">build definitions</a>. To include a Telerik test in your continuous integration build definition, specify the Telerik test files and any test settings files you wish to run in the "Automated Tests" section found on the Process tab of the build definition.

![Build definitions][1]

* **Test Assembly Filespec**: Specify which .tstest files to run. Takes wildcards.

* **TestSettings File**: Specify which .testsettings file to use. For more information on creating a custom testsettings file, see our <a href="/features/test-runners/mstest" target="_blank">MSTest</a> user guide article.

You can set the Test Assembly Filespec to "**\*.aii" This causes the build to run all of your Test Studio tests using the same .testsettings file. Additional configuration settings may be necessary for <a href="/knowledge-base/silverlight-kb/automate-in-tfs-builds" target="_blank">Silverlight testing in builds</a>.

As part of the TFS build definition you have the option of specifying which test list(s) to execute during the testing phase of the build. If you want to modify this list, or specify specific tests by name you'll have to manually modify the TFSBuild.proj file yourself. Unfortunately (as of Visual Studio 2008 and TFS 2008) there is no GUI allowing you to modify/update the list of tests to run once created.

##Changing the list of TestList's to run##

As part of your project development and testing you may find the need to add a new test list or change the name of an existing one. If this happens (and you want the change to be part of the automated build) you'll have to manually modify the TFSBuild.proj file for your project. Follow these steps:

1. Open your Source Code Explorer window in Visual Studio.

2. Navigate to the root of your project and locate the TFSBuild.proj file.

3. Double click on it to open it for editing.

4. Find the section that specifies the list of test lists to run and modify it to look something like this:

```XML
<MetaDataFile Include="$(BuildProjectFolderPath)/SydneyProject.vsmdi">
  <TestList>BVTsTestList;CoreFeaturesTestList</TestList>
</MetaDataFile>
```

##Modifying the list of individual tests to run##

As part of your project development and testing you may find the need to add a new test or change the name of an existing one. If this happens (and you want the change to be part of the automated build rather than adding or modifying the test list) you'll have to manually modify the TFSBuild.proj file for your project. Follow these steps:

1. Open your Source Code Explorer window in Visual Studio.

2. Navigate to the root of your project and locate the TFSBuild.proj file.

3. Double click on it to open it for editing.

4. Find the section that specifies the list of individual tests to run and modify it to look something like this:

```XML
<PropertyGroup>
  <TestNames>BVT;CoreFeatA;CoreFeatB</TestNames>
</PropertyGroup>
```
##How to run tests in a build without test metadata files and test lists (.vsmdi files)##

Normally when you create a new test project, a metadata file is automatically created and added to the project. If you don't want to use this metadata file to create test lists there's a good blog post on how to do that here: <a href="http://blogs.msdn.com/buckh/archive/2006/11/04/how-to-run-tests-without-test-metadata-files-and-test-lists-vsmdi-files.aspx" target="_blank">http://blogs.msdn.com/buckh/archive/2006/11/04/how-to-run-tests-without-test-metadata-files-and-test-lists-vsmdi-files.aspx</a>.

[1]: /img/advanced-topics/build-server/tfs-builds/fig1.png
