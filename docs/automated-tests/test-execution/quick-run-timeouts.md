---
title: Execution Timeouts in Quick Execution
page_title: Execution Timeouts in Quick Execution
description: "Learn how to adjust the execution timeouts for a quick test execution in Test Studio."
position: 4
---
# Adjust the Execution Timeouts

The **Test** ribbon gives you quick access to the following timeout settings:

* **Wait On Elements**&mdash;Sets the amount of time to wait for an element to appear on the page. When the set time expires and the test can't locate the element on the page, the test will fail with an __Element not found__ error. The default value is 15 seconds. Depending on the application's overall performance, you may need to increase or decrease it.

* **Client Ready**&mdash;Sets the amount of time to wait for a page to return __ReadyState__, or to stop loading any content after loading a new page from the application under test. In WPF testing, the **Client Ready** timeout defines the time to wait for the initialization of the desktop app.

These two timeouts are set on a project level, and you can modify these in the project's settings. The **Test** ribbon allows you to quickly change their default values for the current project.

![Timeouts][10]

[10]: /img/automated-tests/test-execution/quick-run-timeouts/fig10.png
