---
title: Run Failure with Status 500
page_title: Run failure with status 500 (Windows XP)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Run failure with status 500 (Windows XP Only)

## PROBLEM

Remote run fails with error status 500 and no test is run.

## SOLUTION

Disable FIPS and restart Telerik Storage Service:

1.&nbps; Open administrative tools from the control panel

![Administrative tools][1]

2.&nbsp; **Disable System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing**

![System cryptography][2]

3.&nbsp; Stop Test Studio Test Runner

4.&nbsp; Restart the Telerik Storage Service

![Services][3]

![Restart][4]

[1]: /img/troubleshooting-guide/scheduling-issues-tg/run-failure-status-500/fig1.png
[2]: /img/troubleshooting-guide/scheduling-issues-tg/run-failure-status-500/fig2.png
[3]: /img/troubleshooting-guide/scheduling-issues-tg/run-failure-status-500/fig3.png
[4]: /img/troubleshooting-guide/scheduling-issues-tg/run-failure-status-500/fig4.png