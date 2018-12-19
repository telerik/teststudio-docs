---
title: Missing Execution Server
page_title: Missing Execution Machine
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Missing Execution Machine

## PROBLEM

After clicking the Manage button in the Project view to open the Machines Viewer dialog, an Execution Machine is missing from the list.

## SOLUTION


- The Execution Server may not be running. On the execution machine, open the Start Execution Server dialog.
- The Execution Server may not be registered to the Scheduling Server.
  - On the execution machine, right-click the Test Studio icon in the System Tray and click Open.
  - In the Test Studio Test Runner window, confirm that the Execution Server is connected to the correct Scheduling Server URL. If not, click Change location... and enter the correct URL.

> If the Change button does not appear, <a href="/troubleshooting-guide/scheduling-issues-tg/no-change-button" target="_blank">update your Scheduling Client configuration file</a>.
