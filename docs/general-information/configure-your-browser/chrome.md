---
title: Chrome
page_title: Configure Chrome for Test Studio Automation
description: "Configure Chrome to use for testing with Test Studio. Prerequisites for testing against Chrome with Test Studio. Chrome extension not found."
position: 1
---

# Configuring Chrome for Test Studio Automation #

To configure Google Chrome for web automation with Test Studio following steps need to be performed:

## 1. Install Progress Extensions

Install the latest Chrome extension from the Chrome Web Store:

**Test Studio 2017 R3 (v. 2017.3.1010) And Later**

There is a single extension combining recording and execution: <a href="https://chrome.google.com/webstore/detail/progress-test-studio-exte/gegcllkonmciadpdldechnepmjildoan" target="_blank">**Progress Test Studio Extension**</a>.
<br>

**Test Studio 2017 R2 SP1(v. 2017.2.824) And Earlier**

There are two seaprate extensions available - one for recording and one for execution - <a href="https://chrome.google.com/webstore/detail/telerik-test-studio-chrom/fiahpmmidlchdfcdpckaclkancbnbgnl" target="_blank">**Progress Test Studio Chrome Recorder**</a> and <a href="https://chrome.google.com/webstore/detail/telerik-test-studio-chrom/pncoonbpgmlbbjnnmaindchmjckkjcdb" target="_blank">**Progress Test Studio Chrome Execution**</a>

>If you face any troubles when installing or enabling the extensions please expand the <a href="#Extension_Install">Extension Install Procedure</a> section below.

## 2. Browser Calibration

To ensure flawless and consistent automation process there are some settings to apply to the browser. We call this browser calibration and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box and no manual interaction is required.<br><br>

>If you need to double check manually if all settings are correct expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.<br><br>

> <p>If your Chrome browser has an active <strong>Google Apps session</strong> (for example, you are logged into GMail), automatic calibration will not work as expected. To use automatic configuration, log out of your Google account first.</p><p></p>
<p></p>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Extension_Install" style="color:black; text-decoration: none;";> Extension Install Procedure <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

1.&nbsp; The Chrome extension is not automatically installed with the Test Studio installation.<br><br>
In case you haven't performed the above recommendation to install the Progress extension manually when you first start recording against Chrome the browser will load the recording start page and will try to load the extension. If that is missing the recorder will search for it for the set ClientReady Timeout (the default is 60 seconds).<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig14.png" alt="Wait For Extension"><br><br>

2.&nbsp; In case the Progress extension is not yet loaded after that timeout a link to the Web Store will be displayed to install the extension.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig10.png" alt="Get Extension"><br><br>

3.&nbsp; By clicking on <strong>Get It Free From Chrome Web Store</strong> you will be directly navigated to the Progress extension in the Web Store.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig11.png" alt="Extension In Store"><br><br>

4.&nbsp; By clicking the <strong>Add to Chrome</strong> button the extension will be added after confirmation. <br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig12.png" alt="Add Extension Confirmation"><br><br>

5.&nbsp; The version of an installed extension could be double checked by clicking on its icon located on the right of the address bar.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig13.png" alt="Extension Version"><br><br>

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

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> located in the upper right corner of the browser <strong>More tools > Extensions</strong>.<br><br>

2.&nbsp; Ensure that the <strong>Progress Test Studio Extension</strong> is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig2.png" alt="Extensions"><br><br>

<h3>Zoom Level Set to 100%</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Use the plus (+) and minus (-) buttons next to <strong>Zoom</strong> to set it to 100% (or use the keyboard shortcut: Ctrl + 0).<br><br> 

<img src="/img/general-information/configure-your-browser/chrome/fig3.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br><br>

4.&nbsp; Locate the <strong>Downloads</strong> section.<br><br>

5.&nbsp; Enable <strong>Ask where to save each file before downloading</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig4.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br><br>

4.&nbsp; Locate the <strong>Privacy and security</strong> section.<br><br>

5.&nbsp; Click <strong>Content Settings</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig5.png" alt="Pop up blocker"><br><br>

6.&nbsp; Under <strong>Popups</strong> section enable <strong>Allowed</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig6.png" alt="Pop up blocker"><br><br>

<h3>Allow All Sites to Run JavaScript</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br> <br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br> <br>

4.&nbsp; Locate the <strong>Privacy and security</strong> section. <br> <br>

5.&nbsp; Click <strong>Content Settings</strong>.<br><br>

6.&nbsp; Under <strong>JavaScript</strong> enable <strong>Allowed</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig7.png" alt="Allow JavaScript"><br><br>

<h3>Unblock Third-Party Cookies and Site Data</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner <strong>Settings > Advanced > Privacy and security > Content Settings > Cookies </strong>.<br><br>

2.&nbsp; Enable <strong>Allow sites to save and read cookie data (recommended)</strong>.<br><br>

3.&nbsp; Disable <strong>Block third-party cookies</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig8.png" alt="Allow Cookies"><br><br>

<h3>Allow all Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on <img src="/img/general-information/configure-your-browser/chrome/fig1.png" alt="chrome settings button"> in the upper right corner <strong>> Settings > Advanced > Privacy and security > Content Settings</strong>.<br> <br>

2.&nbsp; Under <strong>Automatic Downloads</strong> section enable <strong>Allow all sites to download multiple files automatically</strong> .<br><br>

<img src="/img/general-information/configure-your-browser/chrome/fig9.png" alt="Automatic Download"><br><br>

<hr/>

</div>
</div>

<h3>See also:</h3>

* <a href="/troubleshooting-guide/browser-inconsistencies-tg/extensions-disabled-in-chrome" target="_blank">Chrome Extensions Disabled or Missing</a>


<script>
$(".toggle_container").hide();
    
    $("p.trigger").click(function(){
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
</script>


