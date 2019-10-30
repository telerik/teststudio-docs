---
title: Edge Chromium
page_title: Configure Edge Chromium for Test Studio Automation
description: "Configure Edge Chromium to use for testing with Test Studio. Prerequisites for testing against Edge Chromium with Test Studio. Edge Chromium extension not found."
position: 1
---

# Configuring Edge Chromium for Test Studio Automation #

The new Microsoft Edge based on Chromium is supported both for recording and execution in Test Studio web tests. To configure Edge Chromium for web automation with Test Studio you need to perform the following steps.

## 1. Install Progress Extensions

Install the latest Edge Chromium extension for Test Studio. Currently the Edge browser is still in Beta state of its development phase, so the extension package can be downloaded directly from the Test Studio documentation and it can be installed in browser's *Developer mode* only.

Here are the necessary actions to install the extension.

1. <a href="/downloads/Progress_TestStudio_Extension.zip" target="_blank">Download the Test Studio extension</a> for Edge Chromium.

1. Unzip the downloaded archive into a folder.

1. Open Edge and navigate to Settings -> Extensions.

1. Enable *Developer mode*.

1. Click on the *Load unpacked* button and browse to the folder with the unzipped extension package.

1. Enable the Progress Telerik Test Studio extension if needed.

> If you face any troubles when installing or enabling the extensions please expand the <a href="#Extension_Install">Extension Install Procedure</a> section below.

## 2. Browser Calibration

To ensure flawless and consistent automation process there are some settings to apply to the browser. We call this browser calibration and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box and no manual interaction is required.<br><br>

> If you need to double check manually, if all settings are correct, expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.<br><br>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Extension_Install" style="color:black; text-decoration: none;";> Extension Install Procedure <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

The Edge Chromium extension is not automatically installed with the Test Studio installation. and you need to add it manually. As of now the Beta edition of MS Edge does not support all extension from the Google store including the Test Studio one and you need to load it as a developer extension. Below you can find detailed description of the necessary steps.

1.&nbsp; Download the Progress Telerik Test Studio extension from <a href="/downloads/Progress_TestStudio_Extension.zip" target="_blank">here</a>.<br><br>

2.&nbsp; Unzip the downloaded package into any local folder.<br><br>

3.&nbsp; Open Edge and navigate to Settings -> Extensions.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig11.png" alt="Open Extensions"><br><br>

4.&nbsp; Enable *Developer mode*.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig12.png" alt="Enable Developer mode"><br><br>

5.&nbsp; Click on the *Load unpacked* button and browse to the folder with the unzipped extension package.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig13.png" alt="Load Unpacked"><br><br>

6.&nbsp; Ensure the Test Studio extension is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig14.png" alt="Test Studio extension"><br><br>

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

<h3>Enable Extensions</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser <strong>Settings -> Extensions</strong>.<br><br>

2.&nbsp; Ensure that the <strong>Progress Telerik Test Studio Extension</strong> is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig2.png" alt="Extensions"><br><br>

<h3>Zoom Level Set to 100%</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Use the plus (+) and minus (-) buttons next to <strong>Zoom</strong> to set it to 100%.<br><br> 

<img src="/img/general-information/configure-your-browser/edge-chromium/fig3.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Downloads</strong> section.<br><br>

4.&nbsp; Enable <strong>Ask where to save each file before downloading</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig4.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Pop-ups and redirects</strong> section.<br><br>

5.&nbsp; Disable the <strong>Block</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig6.png" alt="Pop up blocker"><br><br>

<h3>Allow All Sites to Run JavaScript</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>JavaScript</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allowed</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig7.png" alt="Allow JavaScript"><br><br>

<h3>Unblock Third-Party Cookies and Site Data</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Cookies and site data</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allow sites to save cookies</strong> option.<br><br>

6.&nbsp; Disable the <strong>Block third-party cookies</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig8.png" alt="Allow Cookies"><br><br>

<h3>Allow all Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Automatic downloads</strong> section.<br><br>

5.&nbsp; Enable the <strong>Ask when site tries to download multiple files</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig9.png" alt="Automatic Download"><br><br>

<h3>Allow Extension from Other Stores</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Extensions</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Enable the <strong>Allow extensions from other stores</strong> option.<br><br>

<img src="/img/general-information/configure-your-browser/edge-chromium/fig10.png" alt="Allow Extension from Other Stores"><br><br>

<hr/>

</div>
</div>


<script>
$(".toggle_container").hide();
    
    $("p.trigger").click(function(){
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
</script>


