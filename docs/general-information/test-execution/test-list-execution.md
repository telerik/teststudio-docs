---
title: Test List Execution
page_title: Test List Execution
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /getting-started/test-list-execution
position: 0
---
# Test List Execution

Once there is a set of test scripts designed and configured to run consistently and smoothly as standalone tests, these can be included in a test list. Test lists can be executed as <a href="/features/scheduling-test-runs/schedule-execution" target="_blank">scheduled jobs</a>, both locally and on remote machines.

Test Studio provides a rich set of <a href="/getting-started/test-execution/test-list-settings" target="_blank">test list settings</a> to help for stable execution of the test suites and easier debugging in case of failures. Below are listed some of the most useful settings, which can be applied to enhance the implemented automation process.

## Automatic Re-run of Failed Tests

Enabling the setting to automatically rerun the failed test will be helpful in the cases of a temporary issue with connectivity or application accessibility. Any failed tests will be executed automatically after the test list execution finishes. Hence, the amount of fake failures will be signifcantly reduced.

![Automatic Rerun Setting][3]

The <a href="/getting-started/test-results/analyze-test-results#automatic-re-run-of-failed-tests-results" target="_blank">results of the second automatic execution</a> will be listed under the initial failed result of the same test. It will be marked with an exclamation mark.

> __Note:__ The tests need to be written as autonomous tests - created in a way to be executed on their own, without the use of previous tests run before them in a list to make them work properly.

## Recording of Test List Execution

Observing the test list execution usually turns out to be helpful to understand what caused the faulure. Of course, there is no way to always keep an eye on the execution. The test list execution recording feature of Test Studio, though, allows you to capture the desktop. You can choose between disabled screeen recording and enabled always or on failure only.

![Screen recording Settings][4]

Below are listed the settings related to Screen Recording of test list execution with additional notes related to each one.

* __Recording Codec__
   
Supported codecs are:
   - Motion JPEG (Biggest file size)

   - X264: [x264 download page](https://sourceforge.net/projects/x264vfw/)

   - Xvid: [Xvid download page](https://www.xvid.com/download/)
   
After installing XVID, _"Display encoder status"_ encoder setting must be disabled. From Windows Start menu open _"Encoder Config"_ ->

![Windows Start Menu][1]

Click _"Other Options.."_ -> Uncheck _"Display encoder status"_

![XVID config][2]

> The default selected codec __MJPEG__ can be used without any further adjustments. <br/> 
> In order to use __Xvid or X264__ codecs, they must be installed on the execution machine (for local and Visual Studio runs on the local machine, and for remote runs, on the machine where test list will be executed)

* __Recording FPS__ - Sets captured video frames per second. Lower number produces smaller files.

* __Recording mode__ - Sets recording mode. There are three different recording modes:
    - Off (Default) - In this mode no video recordings are created.

    - Always - Video recordings for all executed tests are saved.

    - OnFail - Only video recordings for failed tests are saved.

* __Recording output location__ - Sets path to output location for all video files. If no value is set, for local test list runs default location is project results folder. __Always set location for remote or Visual Studio runs.__
   
> For remote executions best practice is to use a shared folder accessable from all remote execution agents. <br/>

* __Recording scale__ - Sets downscaling of the recorded video in percents. From 10 to 100 <br/>

	- _Example:_ If set to 100 the original screen resolution is preserved. When the scale is set to 50 % the resolution of video is halved.
   
> Lower number produces smaller files, but decreases video quality.

*  __Recording size limit__ - Sets file size limit in megabytes, 0 is unlimited size. 

> If the limit is reached, video recording will be stopped before the test execution ends.

[1]: /img/getting-started/test-execution/test-list-execution/fig1.png
[2]: /img/getting-started/test-execution/test-list-execution/fig2.png
[3]: /img/getting-started/test-execution/test-list-execution/fig3.png
[4]: /img/getting-started/test-execution/test-list-execution/fig4.png
