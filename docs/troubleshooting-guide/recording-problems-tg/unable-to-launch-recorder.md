---
title: Unable to Launch Recorder
page_title: Unable to Launch Recorder
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/troubleshooting_guide/recording-problems/unable-to-launch-recorder.aspx, /user-guide/troubleshooting_guide/recording-problems/unable-to-launch-recorder
position: 1
published: false
---
# Unable to Launch Recorder

## PROBLEM

Attempting to start the recorder from Test Studio's GUI results in an error. 

![GUI][1]

The most common errors are:

- Unable to launch recorder.

- Failed to launch the browser.

- Connecting to recorder timed out.

- Exception thrown attempting to launch Internet Explorer. Please make sure Internet Explorer is properly installed and you are able to launch it.


## SOLUTION

- **Run Visual Studio as Administrator**

If you are using the VS plugin, ensure you run Visual Studio as Administrator. <a href="http://www.sevenforums.com/tutorials/11841-run-administrator.html" target="_blank">Here</a> are instructions.


- **Reset Internet Explorer Settings**

Go to **Tools > Internet Options > Advanced** tab. Click the **Reset** button and proceed with resetting IE to its default state. After, ensure you configure IE as mentioned in the next bullet point.

![Reset][2]

- **Configure IE**

In order to optimize IE for recording and playback of tests you have to configure it as described <a href="/getting-started/configure-your-browser/internet-explorer" target="_blank">here</a>. Configuring IE correctly might resolve the issue. You can also try resetting IE to default settings before introducing the new configuration.

- **Uninstall Test Studio and reinstall it**

This might resolve the issue, particularly if you've previously upgraded Test Studio. Uninstalling and then installing again will not cause any data loss - all your projects and tests will still be there. You can download it from Telerik's site after logging into your account. After you download it, you'll need to activate it with your license again - this works the same way whether you're using a trial or paid license.  

- **Ensure Test Studio is using x86 IE (Windows 7 or below)**

If you are using a 64-bit version of Windows below Windows 8, please do the following:

1.&nbsp; Load the project in Visual Studio.

2.&nbsp; Right-click the test project that contains the test.

3.&nbsp; Choose properties.

4.&nbsp; Click the Build tab.

5.&nbsp; Change the Platform Target from Any CPU to x86.

6.&nbsp; Save the changes and re-test execution.


This ensures the 64-bit version of IE is not launched (which Test Studio is not compatible with in Windows 7 or below).

- **Uninstall older versions of Test Studio or Design Canvas (Test Studio's precursor)**

It's possible to have different installations running in parallel. Remove all installations apart from the most recent one (i.e. the one you're planning to use).

- **Temporarily disable all Internet Explorer Add-ons**

Attach the recorder to an instance of IE with add-ons disabled. This is how to do it in Windows 7:

  * Click *Start > All Programs > Accessories > System Tools > Internet Explorer (No Add-ons)*

A new instance of instance of IE is started. Now open a Test Studio project. You'll notice there's an arrow below the Record button. Click on the arrow to open a drop-down menu with IE instances you can connect to. Choose the "Add-ons disabled" instance.

![No addons][3]

If recording works, then an IE add-on is the problem. Consider which IE add-ons could be causing the issue and uninstall them.

- **Migrate Test Studio to a different machine**

This problem is uncommon and hard to reproduce. In our experience, using a different machine to run Test Studio will almost certainly solve the issue. If this is possible for you and none of the other solutions worked - please consider it. Uninstall the current instance of Test Studio and reuse your license on a different instance.

[1]: /img/troubleshooting-guide/recording-problems-tg/unable-to-launch-recorder/fig1.png
[2]: /img/troubleshooting-guide/recording-problems-tg/unable-to-launch-recorder/fig2.png
[3]: /img/troubleshooting-guide/recording-problems-tg/unable-to-launch-recorder/fig3.png