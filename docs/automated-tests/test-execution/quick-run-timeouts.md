---
title: Execution Timeouts in Quick Execution
page_title: Execution Timeouts in Quick Execution
description: "Test Studio Quick test Execution. Test Studio test run. annotated test run. Global Timeouts in Test Studio project. Visual debugger options in Test Studio. Set preferred browser for test runs and test recording. Quick run Execution log "
position: 3
---
# Adjust the Execution Timeouts

The **Test Ribbon** in Test Studio allows you to trigger a quick test execution. Along with that it provides quick access to some useful project settings.

The **Wait on elements** timeout sets the amount of time, which will be waited for an element to exist on a page. When the set time passes and the element cannot be located on the page, the test will fail with _'Element not found'_ error. The default value is 15 seconds and depending on the application overall performance, you may need to increase/decrease it.

The **Client ready** timeout sets the time to wait for a page to return _ReadyState_, or to stop loading any content after loading a new page from the application under test. In the terms of WPF testing, the **Client ready** timeout defines the time to wait for the desktop app to be initiated.

These two timeouts are set on project level and you can modify these in the Project settings. The **Test Ribbon** allows you quick access to change their default values for the current project.

![Timeouts][10]

[10]: /img/automated-tests/test-execution/quick-run-timeouts/fig10.png
