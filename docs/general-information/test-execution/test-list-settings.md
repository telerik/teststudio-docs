---
title: Test List Settings
page_title: Test List Settings
description: "Test Studio Test List Settings. Change the browser for a test list run. RunnerResponseTimeout. UnexpectedDialogAction. KillBrowserProcessOnClose KillBrowsersBeforeStart Test list baseURL"
position: 4
---
# Test List Settings #

**Standalone version**: On the Test **List tab**, highlight a test list and click the **Edit Settings** button in the Edit ribbon.

**VS plugin**: Double click **Local.testsettings** under **Solution Items** in the Solution Explorer.

<table id="no-table">
	<tr>
		<td>![Test Studio][1] <br><br>**Standalone version**</td>
		<td>![VS][2] <br><br>**VS plugin**</td>
	</tr>
<table>

> To create a **Test Settings file** in Visual Studio, right click **Solution Items and select Add > New Item**. Click Test Settings under **Installed Templates**, customize the name if desired, then click Add. Further directions on how to add a settings file are available <a href="/knowledge-base/visual-studio-kb/test-explorer-settings" target="_blank">here</a>.

This opens a dialog box that shows all of the possible configuration settings for that test list. Change the settings as needed for your test list.

<table id="no-table">
	<tr>
		<td>![Test Studio][3] <br><br>**Standalone version**</td>
		<td>![VS][4] <br><br>**VS plugin**</td>
	</tr>
<table>

## General Tab ##

* ***Annotation***
	* **AnnotateExecution** - whether to highlight and annotate the target element that the current action is being executed against.
	* **AnnotationMode** - the annotation mode when annotation is enabled.
* ***Desktop***
	* **ExecuteInDevelopmentTests** - execute tests that are marked as In Development - if checked.
	* **SimulatedMouseMoveSpeed** - the simulated mouse move speed for Desktop.Mouse.Move()/DragDrop() operations in pixel/msec. Typically between: 0.1f - 0.5f
* ***Execution***
	* **ClientReadyTimeout** - the timeout (in msec) to wait for a client to be ready after initial launch and after executing a command.
	* **DisableDialogMonitoring** - enable/disable handling of dialog windows.
	* **ElementImageSearchDelay** - the timeout (in msec) to wait before starting the backup search by image.
	* **ElementImageSearchTimoeout** - the timeout (in msec) for searching the image on page.
	* **ElementWaitTimeout** - the wait on elements timeout used during execution. Overrides the setting applied on project level.
	* **EnableImageSearch** - enable/disable the usage of recorded element images as backup search during test execution.  Overrides the setting applied on project level.
	* **ExecuteCommandTimeout** - the timeout (in msec) to wait for a command request to execute.
	* **ExecutionDelay** - the length of execution delay (in msec) to insert between commands. Note: Some test steps represent multiple commands.
	* **RerunFailedTests** - enable/disable automatic rerun of failed tests.
	* **RunnerResponseTimeout** - how long to wait (in msec) for a response from ArtOfTest.Runner.exe before, we decide that the runner is unresponsive. A value of 0 turns that off. The timer is being reset for each test in the test list. </br>
	
	</br>

	*The main purpose of this timer is to terminate the ArtOfTest.Runner.exe, if it hangs for some reason. If the timeout is reached, the current test run will be terminated despite of the actual execution state  - therefore it is recommended to set a timeout that exceeds the duration of the longest test in the test list with a couple of minutes.*
	* **ScrollOnImageSearch** - enable/disable scrolling of the page when searching an element by image. Overrides the setting applied on project level.
	* **SearchByImageFirst** - enable/disable search by image before searching by element's find expression. Overrides the settings applied on project level.
	* **UnexpectedDialogAction** - specifies the action that the DialogMonitor should take when it encounters unexpected dialogs.
	* **WaitCheckInterval** - the wait interval (in msec) to use between checks for all the *Wait.For* methods.
	* **XMultiMgr** - whether or not to use WebAii 1.1 style connections. When set - multiple Manager objects can co-exist on the machine.
* ***Log***
	* **CreateLogFile** - whether or not to create a log file on disk.
	* **LogAnnotations** - whether or not to log annotations to the log file.
	* **LogLocation** - the location where to perform the logging.
* ***Screen Recording***
	* **RecordingCodec** - the screen recording coded to be used. MJPEG = Motion JPEG (default selected), X264 = x264vfw - H.264/Mpeg-4 AVC codec, XVID = Xvid MPEG-4 Codec. The X264 or XVID codecs need to be additionally installed in order to use them.
	* **RecordingFPS** - sets captured video frames per second. Lower number produces smaller files.
	* **RecordingMode** - sets when a video of the execution to be recorded.
	* **RecordingOutputLocation** - sets path to output location for all video files.
	* **RecordingScale** - sets downscaling of the recorded video in percents. From 10 to 100.
	* **RecordingSizeLimit** - sets file size limit in megabytes, 0 is unlimited size. If the limit is reached, video recording will be stopped before the test execution ends.

## Web Tab ##

* ***APS.NET***
	* **AspNetDevServerPort** - the ASP.NET development server port to use, if enabled. If set to -1, a random port is generated each time the manager is created.
	* **LocalWebServer** - the local web server to use. When set to AspNetDevelopmentServer, the ASP.NET development server is started.
	* **WebAppPhysicalPath** - the path to the application to test when running under the ASP.NET development server.
* ***Browser***
	* **AutoCalibrateBrowsers** - whether or not to automatically calibrate the installed browsers on the execution machine(s) that are selected for execution of the test list. 
	* **Browser** - the default browser to launch.
	* **EnableUILessRequestViewing** - whether to allow debugging of UI-Less page requests using a UI browser, like IE.
	* **KillBrowserProcessOnClose** - whether to kill the browser process when closing the browser.
	* **KillBrowsersBeforeStart** - kill all executing browser instances before test lists starts.
	* **RecycleBrowser** - when set to true, one instance of the browser is launched and recycled throughout all tests until *Manager.Dispose* is called.
	* **WebComponents** - enable or disable WebComponents support. When creating a test list, the setting gets the value set on project level in the <a href="/features/project-settings/general#web-components" target="_blank">Project Settings General tab</a>. After that the setting is independent from the project level setting.
* ***HttpProxy***
	* **UseHttpProxy** - whether to use the built-in HTTP proxy during automation. Enabling Silverlight will automatically enable the HTTP proxy.
* ***Log***
	* **EnableScriptLogging** - whether to enable script logging.
	* **VerboseHttpProxy** - whether the HTTP proxy produces a high level of tracing output.
* ***MultiBrowser Execution***
	* **ExecutingBrowsers** - Select the browsers against which you will execute the test list. Supported in Test Studio Standalone version only.
* ***Navigation***
	* **BaseUrl** - The BaseURL to use for all NavigateTo commands. When set, NavigateTo steps should use a relative URL (i.e. "~/default.aspx").
* ***Silverlight***
	* **EnableSilverlight** - whether to enable Silverlight automation. Enabling Silverlight will automatically enable the HTTP proxy.
	* **SilverlightApplicationPath** - the web address or local directory from which to load a Silverlight application.
	* **SilverlightConnectTimeout** - the amount of time to wait for a Silverlight application to load before timing out.

## WPF Tab ##

* ***Misc***
	* **DefaultApplicationPath** - represents the default application path for WPF tests.

If your Visual Studio Test List runs for more than 30 minutes and fails with an **Execution Timeout Exceeded** error, change the following setting:

![Timeouts][5]

[1]: /img/general-information/test-execution/test-list-settings/fig1.png
[2]: /img/general-information/test-execution/test-list-settings/fig2.png
[3]: /img/general-information/test-execution/test-list-settings/fig3.png
[4]: /img/general-information/test-execution/test-list-settings/fig4.png
[5]: /img/general-information/test-execution/test-list-settings/fig5.png