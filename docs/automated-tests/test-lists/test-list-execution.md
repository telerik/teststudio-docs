---
title: Execute Test List
page_title: Test List Execution
description: "Test Studio Test List Execution. How to run a test list in Test Studio. Automatic re-run rerun of failed test in a test list. recording options for test list execution in Test Studio"
position: 1
---
# How to Execute a Test List?

The test list execution allows you to run the set of tests together, using different settings, and keeps the generated results. The test lists can be executed locally, or on a remote machine, instantly or scheduled for any time in the future.

The **Test Lists** tab in the Test Studio project is where you can maintain the content of test lists and the runtime settings these will use. You can trigger a single or multiple test lists execution.

## Execute Test List Locally

Switch to the **Test Lists** tab in the Test Studio project and select any of the existing test lists. If there is no test list yet, <a href="/automated-tests/test-lists/test-lists-standalone" target="_blank">create one</a>. Then click the **Run List** button in the *Execution* section of the ribbon.

![Run List Locally][3a]

> __Tip__
><br>
><br>
> You can select multiple test lists using the *Shift* key or *Ctrl* key + click. When you click the **Run List** button, the selected test lists will be executed in their order of selection.

The Test Studio Test Runner launches a command prompt window, which indicates the progress of tests and test list execution.

![Runner][4a]

The set browser for the execution, or WPF app, opens and each test executes in sequence. Upon completion, the browser or WPF instance is closed, and the view in Test Studio project is switched to the **Results** tab. The results for each test list run are listed chronologically in the *Results Calendar* view.

![Results][5a]

[3a]: /img/automated-tests/test-lists/test-list-execution/fig3.png
[4a]: /img/automated-tests/test-lists/test-list-execution/fig4.png
[5a]: /img/automated-tests/test-lists/test-list-execution/fig5.png
