---
title: How to Execute Part of a Test
page_title: Execute Part of a Test
description: "Learn how to execute specific steps from a test in Test Studio."
position: 1
---
# Partial Test Execution

While you improve saved tests, you may often need to execute only a part of a test. For these cases, Test Studio provides the ability to combine test recording and partial test execution.

You can access the options for partial test execution only during a test recording session. The partial test execution is useful when debugging a failing step and when you need to add new steps in the middle of a test.

To run a partial test:

1. Right-click a test step to open the context menu.

1. Hover over __Run__ to reveal the following partial test options:

   - [__To Here__](#run-to-here)
   - [__From Here__](#run-from-here)
   - [__Selected Step(s)__](#run-selected-steps)

## Run To Here

The __To Here__ partial test is available only when you select a single test step. This option always launches a new instance of the selected browser - even if there is an already active recording session.

> __Note__
> <br>
> <br>
> If the project has a <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">preferred browser</a>, it will start automatically. Otherwise, the __Executing__ dialog appears, and you can select the desired browser for the test.

![Run To here][1]

The triggered partial run executes the preceding and the selected test steps. Once the step execution finishes, the executing browser stays opened, presents the current state of the tested application, and gets a recorder attached.

![Run To here finished][2]

> __Tip__
> <br>
> <br>
> The recorder attached to the browser is enabled, captures all actions against the page, and then records them in the active test.
> <br>
> To debug the test, pause the recorder.

The partial test run generates a complete execution log. If an executed step fails before the test reaches the selected to-here step, the execution log lists the failure details, and the recorder still gets attached to the browser.

## Run From Here

The __From Here__ partial test is available only when you select a single test step. The partial test executes the selected step and all subsequent steps. The partial test runs in an existing browser instance with an attached recorder.

![Run From here][3]

The partial test run generates a complete execution log. If an executed step fails, the execution log lists the failure details, and the recorder stays attached to the browser.

![Run From here finished][4]

## Run Selected Steps

The __Selected Steps__ partial test is available only when a recording session is active and one or more subsequent steps are selected. The steps are executed in the order listed in the test.

![Run Selected Steps][5]

The partial test run generates a complete execution log. If an executed step fails, the execution log lists the failure details, and the recorder stays attached to the browser.

![Run Selected Steps finished][6]

> __Note__
> <br>
> <br>
> When you use __Form Here__ and __Selected Steps__, the attached recorder stays in the state it was before you triggered the partial test - enabled or paused.
> <br>
> To debug the test, pause the recorder. To continue recording, __enable the recording__.

[1]: /img/automated-tests/test-execution/partial-test-execution/fig1.png
[2]: /img/automated-tests/test-execution/partial-test-execution/fig2.png
[3]: /img/automated-tests/test-execution/partial-test-execution/fig3.png
[4]: /img/automated-tests/test-execution/partial-test-execution/fig4.png
[5]: /img/automated-tests/test-execution/partial-test-execution/fig5.png
[6]: /img/automated-tests/test-execution/partial-test-execution/fig6.png