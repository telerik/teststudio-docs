---
title: Edge Chromium
page_title: Configure Edge Chromium for Test Studio Automation
description: "Configure Edge Chromium to use for testing with Test Studio. Prerequisites for testing against Edge Chromium with Test Studio. Edge Chromium extension not found."
position: 1
---

# Configuring Microsoft Edge for Test Studio Automation 

The document describes the steps to enable Edge Chromium browser for test recording and execution.

Edge Chromium is one of the browsers supported from Test Studio for web apps automation. To start using the browser for test recording and execution you only need to apply the specific set of settings called calibration.  

## Browser Calibration

To ensure a flawless and consistent automation process, there is a list of browser settings which Test Studio requires. We call this **browser calibration** and you can easily apply the specific configuration through the __Project settings__ in the dedicated <a href="/features/project-settings/browsers" target="_blank">__Browsers tab__</a>. You can open it in a web test through the <a href="/automated-tests/test-execution/quick-run-browsers#calibrate-browsers" target="_blank">Test ribbon quick access options</a>. 

![Calibrate browser quick access](/img/automated-tests/test-execution/quick-run-browsers/fig2.png)

## Using Extension for Edge Chromium Automation (Optional)

By default Test Studio projects are __set to use Edge Chromium without extension__. Along with that, there is the option to run Edge Chromium automation with the help of an extension. The <a href="https://chrome.google.com/webstore/detail/progress-test-studio-exte/gegcllkonmciadpdldechnepmjildoan" target="_blank">__Progress Telerik Test Studio Extension__</a> is officially distributed in the Chrome web store and is available for download and installation (Edge Chromium supports adding extensions from the Chrome web store). 

### Enable Project for Edge Chromium Automation with Extension

If you choose to use Edge Chromium for recording and execution with the extension, you need to __change a setting in the Test Studio project__. The <a href="/features/project-settings/browsers" target="_blank">project setting is listed under the __Browsers__ tab</a> and is named __Use browser extension(Chrome/Edge Chromium)__. This option is disabled by default, but you can __check the checkbox__ to set Test Studio to __start the Edge Chromium browser for this project with the extensions__.

![Enable UseBrowserExtension](/img/prerequisites/browser-config/disable-extension.png)

> __Tip__
> <br>
> <br>
> You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).<br><br>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Extension_Install" style="color:black; text-decoration: none;";> Extension Install Procedure <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>


1.&nbsp; When you start recording against Edge, but the Progress extension is not installed, the browser will load the recording start page and will try to load the extension. The recorder will search for the extension for the period that is defined in the *ClientReady* Timeout (the default is 60 seconds).<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig11.png" alt="Wait For Extension"><br><br>

2.&nbsp; If the Progress extension doesn't load within the timeout period, a link to the Web Store will be displayed to install the extension.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig12.png" alt="Get Extension"><br><br>

3.&nbsp; By clicking on <strong>Get It Free From Chrome Web Store</strong> you will be directly navigated to the Progress extension in the Web Store.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig13.png" alt="Extension In Store"><br><br>

4.&nbsp; By clicking the <strong>Add to Chrome</strong> button the extension will be added after confirmation. <br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig14.png" alt="Add Extension Confirmation"><br><br>

5.&nbsp; Click on the icon located to the right of the address bar to find the extension's version.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig15.png" alt="Extension Version"><br><br>
<hr/>

</div>
</div>
<p></p>
<p></p>
<p></p>

<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";> Manual Configuration <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

Follow the steps below to manually configure Edge for web automation with Test Studio.

<h3>Enable Extensions</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser. Then navigate to <strong>Settings -> Extensions</strong>.<br><br>

2.&nbsp; Ensure that the <strong>Progress Telerik Test Studio Extension</strong> is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig2.png" alt="Extensions"><br><br>

<h3>Zoom Level Set to 100%</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Use the plus (+) and minus (-) buttons next to <strong>Zoom</strong> to set it to 100%.<br><br> 

<img src="/img/general-information/configure-your-browser/edge-chromium/fig3.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Downloads</strong> section.<br><br>

4.&nbsp; Enable <strong>Ask where to save each file before downloading</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig4.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Pop-ups and redirects</strong> section.<br><br>

5.&nbsp; Disable the <strong>Block</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig6.png" alt="Pop up blocker"><br><br>

<h3>Allow All Sites to Run JavaScript</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>JavaScript</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allowed</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig7.png" alt="Allow JavaScript"><br><br>

<h3>Unblock Third-Party Cookies and Site Data</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Cookies and site data</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allow sites to save cookies</strong> option.<br><br>

6.&nbsp; Disable the <strong>Block third-party cookies</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig8.png" alt="Allow Cookies"><br><br>

<h3>Allow All Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Automatic downloads</strong> section.<br><br>

5.&nbsp; Enable the <strong>Ask when site tries to download multiple files</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig9.png" alt="Automatic Download"><br><br>

<h3>Allow All Sites to Open PDF Files Externally</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Cookies and site permissions->Site Permissions</strong> section.<br><br>

4.&nbsp; Under <strong>All permissions</strong> select <strong>PDF documents</strong>.<br><br>

5.&nbsp; Enable the <strong>Always open PDF files externally</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig11.png" alt="Always open PDF externally"><br><br>

<h3>Allow Extension from Other Stores</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Extensions</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Enable the <strong>Allow extensions from other stores</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig10.png" alt="Allow Extension from Other Stores"><br><br>

<hr/>

</div>
</div>


<script>
window.addEventListener('DOMContentLoaded', function () {
$(".toggle_container").hide();
    
    $("p.trigger").click(function(e){
        e.preventDefault();
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
    });
</script>


