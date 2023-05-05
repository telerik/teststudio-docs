---
title: Clear Browser Cache
page_title: Clear Browser Cache
description: "How to clear the browser cache during a test run in Test Studio. Clear the browser cache in a Test Studio test execution."
position: 4
---
# Clear Browser Cache

The __Clear Browser Cache__ feature allows you to clear cookies, temp files or history from the active browser. This is useful when you want to start a clean test without saved information (like user name and password), or saved state information ("logged in," last visit date, preferences, etc.).

This article demonstrates how to add this type of step into the test.

Choose the __Clear Browser Cache__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Clear Cache Step](/img/features/custom-steps/clear-browser-cache/fig1.png)

This step clears **all** cookies, temp files or history from the active browser. You can choose which of these to delete.

![Clear Cache Step](/img/features/custom-steps/clear-browser-cache/fig2.png)

> **Safari** doesn't support clearing cache.
