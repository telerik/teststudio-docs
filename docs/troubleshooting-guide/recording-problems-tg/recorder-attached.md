---
title: Recorder Must Be Attached
page_title: Silverlight Unable to Attach Recorder
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Silverlight: Unable to Attach Recorder

## PROBLEM

You receive the message below when attaching the Test Studio recorder to an existing browser instance with a Silverlight application loaded.

![Refresh Page][1]

## SOLUTION

This is normal and expected behavior. The technical challenge is that Test Studio injects hooks into the Silverlight application as the browser is downloading the .XAP file. In this case the browser has already downloaded the .XAP file, so Test Studio cannot hook into the already running Silverlight application.

There are two solutions:


1.&nbsp; Click OK on the message above. After the recorder attaches to the browser, click Refresh in the Internet Explorer browser window (pause the recorder first so a "Refresh" step is not recorded). This forces the Silverlight application to reload so Test Studio can inject its hooks and properly record actions and verifications.

2.&nbsp; Attach the recorder to the browser window *before* the Silverlight application is loaded. Pause recording until you reach the desired page so no unwanted steps are inadvertently recorded.


[1]: /img/troubleshooting-guide/recording-problems-tg/recorder-attached/fig1.png