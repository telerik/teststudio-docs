---
title: Can't Launch Exploratory Tool
page_title: Can't Launch Exploratory Tool
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Cannot Launch Exploratory Tool

## PROBLEM

I receive one of the following errors when attempting to launch the <a href="/features/testing-types/exploratory-testing/Overview" target="_blank">Exploratory Testing</a> tool.

- **Internet Explorer**: Feedback.Listener is not running!

- **Firefox**: Cannot launch Telerik Exploratory Tool.

- **Safari**: Telerik Exploratory Testing Extension NaN.

- **Chrome**: Cannot launch Telerik Exploratory Tool.

## SOLUTION

Start the Feedback Listener process manually from the following location, then launch the tool again through the browser.

- **C:\Program Files (x86)\Progress\Test Studio\Bin\Feedback\Telerik.TestStudio.Feedback.Listener.exe**

 The Exploratory Testing tool is currently unable to launch for users with non-administrator rights.

- You may need to right click *Telerik.TestStudio.Feedback.Listener.exe* and select <a href="http://www.sevenforums.com/tutorials/11841-run-administrator.html" target="_blank">Run as Administrator</a>. Then launch the browser in the same fashion.

 