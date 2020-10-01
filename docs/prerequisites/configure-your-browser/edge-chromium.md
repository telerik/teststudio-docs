---
title: Edge Chromium
page_title: Configure Edge Chromium for Test Studio Automation
description: "Configure Edge Chromium to use for testing with Test Studio. Prerequisites for testing against Edge Chromium with Test Studio. Edge Chromium extension not found."
position: 1
---

# Configuring Microsoft Edge for Test Studio Automation 

This document describes the steps to configure Microsoft Edge (Chromium-based) for test recording and execution.

## 1. Install the Progress Extensions

Install the latest Edge extension from the Chrome Web Store - <a href="https://chrome.google.com/webstore/detail/progress-test-studio-exte/gegcllkonmciadpdldechnepmjildoan" target="_blank">**Progress Test Studio Extension**</a>.

> **Note!** Currently, Edge Chromium supports installing extensions from the Chrome store and this will be used until a Test Studio extension is published in the official Edge store.</br>
> If you face any troubles when installing or enabling the extensions please expand the <a href="#Extension_Install">Extension Install Procedure</a> section below.

## 2. Browser Calibration

To ensure a flawless and consistent automation process, there are a few browser settings that we need to apply. We call this **browser calibration** and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box. No manual interaction is required.<br><br>

> If you need to check manually if all settings are correct, expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.<br><br>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Extension_Install" style="color:black; text-decoration: none;";> Extension Install Procedure <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

Follow the steps below if the extension for Edge is not automatically installed during the Test Studio installation.<br><br>

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

<h3>Allow all Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on the *Settings* button in Edge - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Automatic downloads</strong> section.<br><br>

5.&nbsp; Enable the <strong>Ask when site tries to download multiple files</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig9.png" alt="Automatic Download"><br><br>

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
$(".toggle_container").hide();
    
    $("p.trigger").click(function(e){
        e.preventDefault();
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
</script>


