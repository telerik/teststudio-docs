---
title: Responsive Web Testing
page_title: Responsive Web Testing
description: "Responsive Web Testing in Test Studio. What is responsive web testing in Test Studio. How the responsive web testing in test studio works. Use the Chrome and Edge Chromium browsers viewport to simulate different mobile devices and test web pages on these. "
position: 2
---
# Configure a Responsive Web Test

To help you address the needs of your mobile users, Test Studio offers <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">comprehensive features to enable the responsive web UI testing</a>.

Using the **Device Mode** of <a href="https://developers.google.com/web/tools/chrome-devtools/device-mode" target="_blank">Chrome</a> and <a href="https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/device-mode/" target="_blank">Edge Chromium</a> browsers you can simulate different mobile devices and check how a web page behaves on these. With its __Responsive Web test__ Test Studio provides the capability to record and execute tests against such emulated device mode.

The __Responsive Web test__ in Test Studio is a separate type of test, which require some additional settings in order to correctly simulate mobile devices in the Device Mode of Chrome or Edge Chromium. This article describes the necessary adjustments in order to test a web page on a simulated mobile device.

## Create a Responsive Web Test

To add a __Responsive Web test__ to your project, use the respective type of test to create. You can use the option both from the Project Ribbon or from the <a href="/features/project-explorer/overview#project-context-menu-options" target="_blank">Project Explorer context menu</a>.

<table id="no-table">
	<tr>
		<td>![Project Ribbon][1] <br><br>**Project Ribbon**</td>
		<td>![Project Explorer][2] <br><br>**Project Explorer**</td>
	</tr>
<table>

## Configure a Device to Simulate

Open the newly created __web responsive test__ and click the quick access button from the _Test Ribbon_ to open the __Device settings__.

![Quick access device settings button][3]

The default pre-selected option is to manually choose the __width and height of the device display__ to simulate. The preset values are 100/100 and you can enter the desired values in the respective fields. The __User Agent__ field allows you to modify the <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent" target="_blank">User-Agent request header</a> used from the browser for identification toward server and network peers. If left blank, the browser will use its default user agent.

![Default device settings manual setting][4]

### Predefined Devices

For your ease, we have prepared a list of predefined devices, from which you can select and directly set the necessary values for device display size and user agent. Choose a device from the __Device__ dropdown and the __Width__, __Height__ and __User Agent__ values get set according to the selected device and remain grayed out.

![Device settings list of devices][5]

## Record a Responsive Test

1. To trigger a recording session, click the __Record__ button in the _Tests_ ribbon or press **CTRL+R**. In the *Recording* dialog type the URL you want to navigate to, select Chrome or Edge Chromium (these are the browsers supported for recording and execution on simulated mobile devices) and press _Enter_ or click the ***Record*** button. You can choose a URL from your recently used URLs.

	![Choose browser][6]

	> **Note** Selecting the recording browser will be skipped, if you have already set a preferred browser from the <a href="/general-information/test-execution/quick-execution" target="_blank">Test ribbon</a>.

2. Once the selected browser navigates to the desired page, it is shrunk to the predefined width and height of the preselected device and the recorder gets attached to the browser instance. A navigate step is recorded in the _Steps_ pane and you can continue recording the next actions as per the required scenario.

	![Attached recorder][7]

	> __Note!__ In order to simulate the selected mobile device, Test Studio forces the browser to enter in debug mode. This brings a message line __'"Progress Telerik Test Studio Extension" started debugging the browser'__, which cannot be hidden. You can ignore the message and continue recording. <br><br>
	> __Note!__ While recording a test, **do not start another instance of the same browser** until the recording is finished!

3. Let's navigate to the <a href="/general-information/test-execution/quick-execution" target="_blank">Telerik official page</a>, which has responsive design and looks different on different size displays. Record few click steps to navigate to the _Test Studio official_ page through the _All Products_ menu.

	![Recorded steps][8]

4. To exit the recording session, close the browser with the attached Recording toolbar.

## Execute a Responsive Test

> __Note!__ In order to simulate the selected mobile device, Test Studio forces the browser to enter in debug mode. This brings a message line __'"Progress Telerik Test Studio Extension" started debugging the browser'__, which cannot be hidden. You can ignore the message and continue executing the tests. <br><br>
> __Note!__ While a test is being executed **do not start another instance of the same browser or any other application** until the run is finished!

1. Once a test scenario is already recorded, click the **Execute** button in the _Test_ ribbon.

    ![Test Studio](/img/getting-started/first-project/fig08.png)

2. In the _Executing_ dialog select Chrome or Edge Chromium (these are the browsers supported for recording and execution on simulated mobile devices) to run the test against and press _Enter_ or click the ***Run*** button.

    ![Select browser][10]

    > __Note!__ This step will be skipped if you have already set a preferred browser from the <a href="/general-information/test-execution/quick-execution" target="_blank">Test ribbon</a>.

3. Test Studio launches the selected browser, displays the page shrunk in the predefined device display size and executes the steps recorded in the test. The **Execute** button in the _Test_ ribbon is changed to __Abort__ and allows you to stop the test run before it is finished.

    ![Abort Run](/img/getting-started/first-project/fig10.png)

    > __Note!__ If you abort the test execution before it is finished, there will be no results stored.

## Elements in the Responsive Web Test

The __Responsive web test__ is using the same elements as a standard web test. That said, if the page under test uses the same elements in its responsive view, you can reuse already recorded steps from a web test and paste these into the newly created responsive one.

> __Note!__ The elements may look different in the desktop and responsive version of the web page and you may need to additionally <a href="/features/elements-explorer/find-element-by-image" target="_blank">adjust the images for the these</a>, when searched by image.

[1]: /img/features/testing-types/responsive-web/add-responsive-test-ribbon.png
[2]: /img/features/testing-types/responsive-web/add-responsive-test-proj-explorer.png
[3]: /img/features/testing-types/responsive-web/device-settings-button.png
[4]: /img/features/testing-types/responsive-web/device-settings-default-manual.png
[5]: /img/features/testing-types/responsive-web/device-settings-dropdown-list.png
[6]: /img/features/testing-types/responsive-web/trigger-recording-session.png
[7]: /img/features/testing-types/responsive-web/responsive-recording-session.png
[8]: /img/features/testing-types/responsive-web/recorded-steps.png
[10]: /img/features/testing-types/responsive-web/select-exec-browser.png