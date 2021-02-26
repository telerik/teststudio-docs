---
title: How to Execute Part of a Test
page_title: Execute Part of a Test
description: "Test Studio partial test Execution. Run part of a Test Studio test. Execute certain steps of the test. Run test to here. Run test from here. Run selected steps"
position: 1
---
# Partial Test Execution

Quick Test Execution in Test Studio is a key feature to help in identifying any weak spots in the recorded tests and finding the most suitable adjustment for the occasion. While working on improving the tests, you may often find useful to __execute only part of a test__. For these cases Test Studio provides the ability to combine test recording and partial test execution and boost your productivity to a next level.

The options for partial execution are a bit different from the quick test run, as __these are triggered in the context of a recording session__. And although the partial test execution can be really advantageous when debugging a failing step, it could be also very useful, in the case when you need to add new steps in the middle of a test. Let's have a look on the possible options for running a test partially:

- [__To Here__](#run-to-here)
- [__From Here__](#run-from-here)
- [__Selected Step(s)__](#run-selected-steps)

## Run To Here

The partial test run can be triggered from the context menu based on a selected step. All options are listed in the _Run..._ sub-menu. __Run->To Here__ is only active when a single step from the test is selected. This option always __launches a new instance of the selected browser__ - even if there is an already active recording session.

> __Note__
> <br>
> <br>
> If the project uses a <a href="/automated-tests/test-execution/quick-run-browsers#preferred-browser" target="_blank">preferred browser</a>, this will be started automatically. Otherwise, the dialog to select recording browser appears and the run will continue after the browser is selected.

![Run To here][1]

The triggered partial run executes the preceding (including the selected) test step(s). Once the step execution finishes, the __executing browser remains opened, presenting the current state of the application under test, and a recorder gets attached to it__.

![Run To here finished][2]

> __Tip__
> <br>
> <br>
> The __attached recorder to the browser is enabled for recording__. Thus any actions against the page will be captured and recorded in the active test.
> <br>
> Ensure to __pause the recorder__, if you need to debug your test.

Although the run is only partial, it generates a complete execution log for the executed steps. And in case any of the executed steps failed, before the selected one was reached, the failure details are listed in the execution log and the recorder still gets attached to the browser.

## Run From Here

The __Run From Here__ option is only available in the __context of an active recording session__ and a single step selected from a test. It is also listed in the _Run..._ sub-menu. It executes the subsequent steps starting from the selected one in an existing browser instance with attached recorder.

![Run From here][3]

It generates complete execution log, so in case any of the executed steps fails, the failure details are listed in the execution log and the recorder remains attached to the browser.

![Run From here finished][4]

## Run Selected Steps

The option to execute few steps selected from a test, __Run Selected Steps__, is the last listed in the _Run..._ sub-menu. It is only applicable if there is an __active recording session and one or more, but subsequent, steps are selected__. These steps gets executed in the order they are listed in the test.

![Run Selected Steps][5]

This partial run also generates complete execution log, so if any of the selected steps fails to be executed, the complete failing details will be listed in the logging.

![Run Selected Steps finished][6]

> __Note__
> <br>
> <br>
> In the case of _Run Form Here_ and _Run Selected Steps_, the attached __recorder to the browser remains in the same state__ as before the partial run was triggered - enabled or paused for recording.
> <br>
> Ensure to __pause the recorder__, if you need to debug your test, or to __enable the recording__, if you need to continue recording.

[1]: /img/automated-tests/test-execution/partial-test-execution/fig1.png
[2]: /img/automated-tests/test-execution/partial-test-execution/fig2.png
[3]: /img/automated-tests/test-execution/partial-test-execution/fig3.png
[4]: /img/automated-tests/test-execution/partial-test-execution/fig4.png
[5]: /img/automated-tests/test-execution/partial-test-execution/fig5.png
[6]: /img/automated-tests/test-execution/partial-test-execution/fig6.png