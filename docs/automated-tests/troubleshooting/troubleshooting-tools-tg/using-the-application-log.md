---
title: Using the Application Log
page_title: Using the Test Studio Application Log
description: "Using the Test Studio Application Log. How helps me the Test Studio application log. What errors can be identified in the Test Studio Application Log. "
previous_url: /user-guide/troubleshooting_guide/troubleshooting_tools/using_the_application_log.aspx, /user-guide/troubleshooting_guide/troubleshooting_tools/using_the_application_log
position: 1
publish: false
---
# Using the Test Studio Application Log

**What is the application log?**

The <a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> application log is a record of log messages recorded by Test Studio throughout runtime. All records in the application log, are designed to indicate important events and help pinpoint where problems may occur. This is distinct from the execution log, which only records the attempted steps and encountered exceptions during test execution.

**When to turn on the application log?**

Whenever Test Studio behaves differently than expected, an application log can give more information about why. This is especially true for situations other than test failure or code compilation. For example:

- Test Studio generates error messages;

- Test Studio closes unexpectedly;

- Test Studio stops responding;

- Test Studio interacts with other software (TeamPulse, TFS, QC) differently than expected;

- A Test Studio execution browser closes unexpectedly or stops responding during execution;

- Test Studio cannot connect to a browser.

**Generating the application log.**

You can <a href="/knowledge-base/best-practices-kb/generate-application-log" target="_blank">generate an application log</a> from the help tab.

**What to look for in the application log.**

The application log can be useful in many ways to Test Studio support engineers and developers. Users with issues should look for exceptions. 

![Log][1]

These are usually accompanied with error messages that may guide you in troubleshooting. If you are not familiar with the error message, try searching our documentation for it. If you still cannot understand the error, consider attaching a copy of the log to a <a href="/knowledge-base/best-practices-kb/submit-support-ticket" target="_blank">support ticket</a>. 

[1]: /img/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log/fig1.png