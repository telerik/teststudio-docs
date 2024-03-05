---
title: Automate in TFS Builds
page_title: Automate in TFS Builds
description: How to Automate Silverlight Tests in TFS Builds
position: 1
publish: false
---
#How to Automate Silverlight Tests in TFS Builds#

The first step is to setup our Visual Studio solution correctly. It needs to contain three projects:

* The Silverlight application.

* A web project that will host the Silverlight application within a web page.

* A test project that will contain our automated tests.

![SL projects][1]

To create this combination in a fresh and new Visual Studio solution:

1. From **File -> New Project select "Silverlight Application**". This will automatically create a Silverlight application project and a web project that references the new Silverlight application project. Your new Visual Studio solution now shows two projects. Next we'll add a test project to the solution to hold our Test Studio automated tests that will run against the Silverlight application we're developing.

2. Right click on the root node in Solution Explorer and select "Add -> New Project...".

3. Expand the **Telerik** node and select either the "Visual Basic Test Studio Project" or the "Visual C# Test Studio Project". This will add a new test project to your solution as well as add a sample Test Studio test to it. You can keep or delete the sample test because it is not needed for our Silverlight automated testing.
 
At this point you can begin working on your Silverlight application. Once you have something working let's get our first test running against our new Silverlight application. We'll start by recording our test.
 
We will use the ASP.NET development server that comes with Visual Studio to act as our web server hosting our Silverlight application. In order to make recording and playback reliable we need to configure the development server to use a fixed port instead of a variable port. If we were to let it use a variable port and that port number changes between recording and playback, our tests will suddenly start failing on the initial NavigateTo steps.

1. Right click on the xxxxx.Web node in Solution Explorer and select Properties. This will open the properties for the web project.

2. Click Web from the list of tabs on the left.

3. Click Specific Port.

4. Enter a valid port number. Any number between 1024 and 65535 should work just fine.

5. The default settings for everything else should be just fine. Save your changes and close the properties window.

![SL config][2]

To setup for recording we first have to make the Silverlight application run in a browser window without initiating the Visual Studio debugger. In Visual Studio, within the "xxxxx.Web" project, right click on either the .aspx file or the .html file and select "View in browser". This will start the ASP.NET development server to serve up the web pages and Silverlight application locally and then load your Silverlight application in a new browser window. Now that our Silverlight application is running in a browser window, we're ready to launch the Test Studio recorder and record our test.

Now we're going to start recording.

1. Add a new Web test to the test project or open an existing one.

2. Click the Record button in Visual Studio.

3. Copy the URL that appears in the browser window that was previously opened and is showing your Silverlight application.

4. Paste this URL into the IE window that just opened when you clicked Record.

5. Click the Go To arrow button in IE.

6. This should record a NavigateTo step and cause your Silverlight application to appear in our IE recording window.

7. Finish recording and perfecting your test until you're happy with it.

Unfortunately the default properties recorded for the NavigateTo step do not quite work for executing tests using the ASP.NET development server. The change is simple however. We just need to trim the beginning of the URL. Remove the "http://localhost:5008" portion (yours may be different if you use a different port number) of the NavigateUrl property and replace it with a ~ like this:

![Properties][3]

Once you are satisfied that your test meets your needs we need to run it one more time from Visual Studio Test View to insure it will run properly as part of a TFS automated build. In preparation of this we need to create at least a couple of .testsettings files. One will be used for running tests in the TFS build and the other will be used for running tests locally from Test View. Optionally you can add a third .testsettings file that can run tests that won't use the ASP.NET Development Server (such as Test Studio tests that need to hit a live website).

![Solution explorer][4]

Let's configure our LocalAspNetDevServer.testsettings file first.

1. Double click on the to open it.

2. Click Web Test on the left.

3. Click the General tab at the top.

4. If you're using VS 2010, select AspNetDevelopmentServer40 from the "Local Web Server Type" drop down. Otherwise select AspNetDevelopmentServer from the dropdown.

	![Test Settings][5]

5. Set the Local Web Server Port to the same value you used during recording i.e. the same value you entered for the "Specific port" of your xxxxx.web project.

6. Next we need to set the path to our web files for the ASP.NET development server. Click on the File Paths tab and set "Web App Physical Path" to the full path to the xxxxx.web project folder located on your local hard drive e.g. "C:\Users\gibson\Documents\Visual Studio 2010\Projects\SilverlightAppTesting\SilverlightAppTesting.Web".

	![File paths][6]

7. The default setting for rest of the properties should be just fine.

Make sure that LocalAspNetDevServer.testsettings is the active .testsettings file. In Visual Studio click Test then go to Select Active Test Settings and click on LocalAspNetDevServer.testsettings.
 
Now we're ready to test running our application from Test View.

1. Open Test View in Visual Studio.

2. Right click on your test from the list and select Run Selection.

A whole series of events should happen and if everything is setup correctly, your test will run and pass.

1. The ASP.NET Development Server should start up.

	![ASP.NET Development Server][7]

2. An IE window should open and load your Silverlight application.

	![Start test][8]

3. Your test should run and pass.

	![Passed test][9]

We have one more step to perform before checking in our files into TFS source control. Because the Web App Physical Path will be different on your build server than your local machine we need to create another .testsettings file to be used by the automated build. You can open the current LocalAspNetDevServer.testsettings file, save it to a new file, e.g. AspNetDevServer.testsettings, then modify the Web App Physical Path to match where your TFS build machine will place the files during the build process. The correct path is going to be a combination of the TFS server configuration, build server configuration and the location in source control of the project. On my build server the path works out to be "C:\Builds\4\TestLabProject\SilverlightAppTesting\Binaries\_PublishedWebsites\SilverlightAppTesting.Web".
 
The last project level setting we need to change just prior to check-in is to set "Copy to Output Directory" for all of our .aii tests to either "Copy Always" or "Copy if newer". Either setting will work.

![File properties][10]

Now save everything to disk and check-in the entire solution into TFS. We're ready to start working on the build server side of things.
 
In order for Silverlight tests to successfully run we need to configure our TFS Build Service to run as an "Interactive Process".

1. Click Start -> All Programs -> Microsoft Team Foundation Server 2010 -> Team Foundation Administration Console.

2. Click Build Configuration on the left.

3. Click Properties for the Build Service.

4. If your build service is already running, click "stop to make changes".

5. Select "Interactive Process"

6. Enter credentials for a real domain account that has the necessary permissions to access TFS and perform builds.

	![Build server properties][11]

7. Click Start to restart the build service. A new window should open for your interactive build process. You can minimize this window, but do NOT close it. If your close it you effectively shut down your build service which will prevent builds from running.

Now we're ready to put together the build process for our new Silverlight project. Start by creating a new build definition within Visual Studio. I won't go through all of the settings that are required to complete a build definition as the list is extensive. We only need to focus on the "Automated Tests" section found on the Process tab of the build definition.

![Configuration][12]

The above sample is a complex sample that demonstrates how to run some tests using the ASP.NET development server and some tests without the ASP.NET development server. I chose to use a naming convention for all of my tests. Any test that where the name contains "DevServer" will be executed using the ASP.NET development server while any test where the name contains "Live" will also be executed but without the ASP.NET development server. Notice how different .testsettings files are used for the different test groups. I have setup AspNetDevServer.testsettings to start the ASP.NET Development Server and point it to the path of where my Silverlight application was build on my build server. The IESettings.testsettings is configured to not use the ASP.NET Development Server. The "**" part of the Test Assembly Filespec means "recursively search all folders within the solution".
 
For a more simple configuration, you can set the Test Assembly Filespec to "**\*.aii" and not create a second test assembly section. This cause the build to run all of your Test Studio tests using the same .testsettings file.
 
Go ahead and save your build configuration and queue a new build. If everything is configured right your build will run, the automated tests will run and pass. That's it!

![Build SL][13]

![Test Results][14]

[1]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig1.png
[2]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig2.png
[3]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig3.png
[4]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig4.png
[5]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig5.png
[6]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig6.png
[7]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig7.png
[8]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig8.png
[9]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig9.png
[10]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig10.png
[11]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig11.png
[12]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig12.png
[13]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig13.png
[14]: /img/knowledge-base/silverlight-kb/automate-in-tfs-builds/fig14.png

