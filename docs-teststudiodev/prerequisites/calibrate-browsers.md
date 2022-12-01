---
title: Configure Browsers
page_title: Configure Browsers | Test Studio Dev Documentation
description: How to Configure Browsers to Use These to Record and Execute Tests with Test Studio Dev
slug: prerequisites/calibrate-browsers
tags: configure. browsers, calibrate
published: True
position: 3
---
<style>
p.trigger{
	margin-bottom:7px;
	margin-top:-5px;
	font-size:1.8rem;

}

	.toggle_container{
	margin-bottom:10px;
}

	.toggle_container p{
	margin:0px;
}

	.toggle_container{
    
	clear: both;
	font-size:100%;
}

</style>

# Calibrate Browsers

A specific set of settings is required to enable each of the supported browsers for test recording and execution with Test Studio Dev and this is called __Browser Calibration__. Some of the browsers also require the installation of an extension.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-overview.html %}
{% endif %}

## Built-in Calibration

We call that the browser is __calibrated__ when the required settings are applied. __Test Studio Dev__ provides a built-in configuration approach which will set all necessary settings for the supported browsers out of the box and no manual interaction is required. To use our built-in feature open the __Test Studio Dev Settings__ window and switch to its __Browser__ tab.

![Open Settings->Browser Tab](images/open-settings-browser.png)

In the __Browser__ tab are listed the installed browsers on the current machine with a _Calibrate/Restore_ button next to each. If a browser is successfully calibrated the button allows you to restore its previous settings.

![Restore](images/restore.png)

If a browser is not yet configured the button allows you to calibrate it.

![Calibrate](images/calibrate.png)

> __Note!__
> <br>
> <br>
> During browser calibration __Test Studio Dev automatically closes__ all currently running browser instances. Ensure there is no important information you might lose if browser gets closed before proceeding with calibration</br></br>

> __Tip__
> <br>
> <br>
> You can check all settings applied from the calibration in the <a href="#manual-settings-to-configure-a-browser">Manual Configuration</a> section below (click the + sign to expand it).

## Enable Chrome and Edge Chromium for Automation

Once Chrome and Edge Chromium browsers are calibrated you can continue with recording and executing the automated tests. 

### Enable Chrome amd Edge Chromium for Automation with Extension

By default Test Studio Dev projects are set to use Chrome and Edge Chromium without extension. Along with that, there is the option to run these two browsers automation with the help of an extension. The <a href="https://chrome.google.com/webstore/detail/progress-test-studio-exte/gegcllkonmciadpdldechnepmjildoan" target="_blank">__Progress Telerik Test Studio Extension__</a> is officially distributed in the Chrome web store and is available for download and installation (Edge Chromium supports adding extensions from the Chrome store).

If you choose to use Chrome for recording and execution with the extension, you need to __change a setting in the Test Studio Dev project__. The <a href="/features/project-settings/overview" target="_blank">project setting is listed under the __Browsers__ tab</a> and is named __Use browser extension(Chrome/Edge Chromium)__. This option is disabled by default, but you can __check the checkbox__ to set Test Studio Dev to __start the Chrome/Edge Chromium browser for this project with the extensions__.

![Enable UseBrowserExtension](images/browser-config/disable-extension.png)

## Enable Firefox for Automation

Firefox browser requires an extension for the purposes of automation testing with __Test Studio Dev__.

The __Firefox__ extension can be found in the Firefox Add-ons Page - <a href="https://addons.mozilla.org/en-US/firefox/addon/progress-test-studio-extension/", target=blank>__Progress Test Studio Extension__</a>.

## Settings Applied from the Calibration

### Internet Explorer

You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).<br><br>

<p></p>
<p></p>

<p><hr></p>
<p></p>
<p></p>
<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";>Manual Configuration <span id="d" style="color:#28a1e2";>+</span></a></p>

<div class="toggle_container">
<div class="block">

<h3>Zoom Level Set to 100%</h3>

1. Go to the higher right of the browser.<br><br>
2. Click Tools button -> <strong>Zoom</strong>.<br><br>
3. Select 100% (or use the keyboard shortcut: Ctrl + 0).<br><br>

<img src="images/internet-explorer/fig1.png" alt="Zoom"><br><br>

<h3>Disable Protected Mode</h3>

1. Click <strong>Tools > Internet Options</strong>. <br><br> 
2. Click the <strong>Security</strong> tab.<br><br>
3. Uncheck the <strong>Enable Protected Mode</strong> checkbox.<br><br>
4. Repeat step 3 for:<br><br>
- <strong>Internet</strong><br><br>
- <strong>Local intranet</strong><br><br>
- <strong>Trusted sites</strong><br><br>

<img src="images/internet-explorer/fig2.png" alt="Protected Mode"><br><br>

<h3>Disable Pop-up Blocker</h3>

1. Click <strong>Tools > Internet Options</strong><br><br>
2. Click the <strong>Privacy</strong> tab.<br><br>
3. Uncheck the <strong>Turn on Pop-up Blocker</strong> checkbox.<br><br>

<img src="images/internet-explorer/fig3.png" alt="Pop up blocker"><br><br>

<h3>Pop-ups Open in a New Window</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. On the <strong>General tab</strong>, click the <strong>Settings</strong> button for </strong>Change how webpages are displayed in tabs</strong>.<br><br>
3. Select <strong>Always open pop-ups in a new window</strong>.<br><br>

<img src="images/internet-explorer/fig4.png" alt="Pop ups open in new window"><br><br>

<h3>Add the Websites to List of Trusted Sites</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click on <strong>Trusted sites</strong>.<br><br>
4. Click the <strong>Sites</strong> button.<br><br>
5. If your site is not secure (uses HTTPS protocol), then uncheck the <strong>Require server verification</strong>... checkbox.<br><br>
6. Enter the URL of your website in <strong>Add this website to the zone</strong> text box. This text box will accept both DNS names and IP addresses.<br><br>
7. Click <strong>Add</strong>.<br><br>
8. Repeat steps 6-7 for each website you'll be testing.<br><br>

<img src="images/internet-explorer/fig5.png" alt="Trusted site"><br><br>

<h3>Disable Trusted Sites Message</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>.<br><br>
4. Scroll down until you find the <strong>Websites in less privileged web content zone</strong> can navigate into this zone under the <strong>Miscellaneous heading</strong>.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="images/internet-explorer/fig6.png" alt="Trusted site message"><br><br>

<h3>Ensure JavaScript Is Enabled</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>Active scripting</strong> setting under the <strong>Scripting</strong> heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="images/internet-explorer/fig7.png" alt="Enable Scripting"><br><br>

<h3>Disable Mixed Content Message</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>Display mixed content</strong> setting under the Micellaneous heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="images/internet-explorer/fig8.png" alt="Disable script content"><br><br>

<h3>Enable File Downloads</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>File download</strong> setting under the Downloads heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>
6.  Repeat steps 3 - 5 for the <strong>Local intranet</strong> and the <strong>Internet</strong> zones.<br><br>

<img src="images/internet-explorer/fig9.png" alt="Downloads"><br><br>

For <strong>IE7</strong> and <strong>IE8</strong> file downloads, uncheck <strong>Close this dialog box when download completes</strong>. The only way to do this is to actually start downloading something and uncheck this checkbox while the download is running.<br><br>
	
<img src="images/internet-explorer/fig10.png" alt="Downloads"><br><br>

For __IE9__ downloads, check __Notify me when my downloads are complete__:<br><br>

1. Click <strong>Tools > View downloads</strong>.<br><br>
2. Click the <strong>Options</strong> link in the lower left.<br><br>
3. Check <strong>Notify me when my downloads are complete</strong>.<br><br>
4. Click <strong>OK</strong><br><br>

<img src="images/internet-explorer/fig11.png" alt="Downloads"><br><br>

<h3>Allow Local Files to Run Unhindered</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Advanced</strong> tab.<br><br>
3. Check <strong>Allow active content to run in files on My Computer</strong> under the <strong>Security</strong> heading.<br><br>

<img src="images/internet-explorer/fig12.png" alt="Local files"><br><br>

<h3>Turn Off AutoComplete</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Content</strong> tab.<br><br>
3. Click the <strong>Settings</strong> button under the <strong>AutoComplete</strong> section.<br><br>
4. In <strong>AutoComplete Settings</strong>, uncheck <strong>Forms</strong> and <strong>User names and passwords on forms</strong>.<br><br>

<img src="images/internet-explorer/fig13.png" alt="Turn of auto-complete"><br><br>

<h3>Windows updates</h3>

The latest Internet Explorer updates should be installed. <br><br>

<strong>Note:</strong> Installing <a href="http://www.microsoft.com/en-us/download/details.aspx?id=44431" target="_blank">KB2987107</a> security update for Internet Explorer 11 helps some customers with recording issues.<br><br>

<h3>Add http://www.w3.org to Trusted Sites</h3>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong>.<br><br>
4. Add <strong>http://www.w3.org</strong> to the trusted sites.<br><br>

<img src="images/internet-explorer/fig14.png" alt="Add http://www.w3.org"><br><br>

</div>
</div>
<p></p>
<p><hr></p>
<p></p>
<p></p>

### Chrome

> <p>If your Chrome browser has an active <strong>Google Apps session</strong> (for example, you are logged into GMail), automatic calibration will not work as expected. To use automatic configuration, log out of your Google account first.</p><p></p>
<p></p>

You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).<br><br>

<p><hr></p>
<p></p>
<p></p>

<p></p>
<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";> Manual Configuration <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

<h3>Enable Extensions</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> located in the upper right corner of the browser <strong>More tools > Extensions</strong>.<br><br>

2.&nbsp; Ensure that the <strong>Progress Test Studio Extension</strong> is enabled.<br><br>

<img src="images/chrome/fig2.png" alt="Extensions"><br><br>

<h3>Zoom Level Set to 100%</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Use the plus (+) and minus (-) buttons next to <strong>Zoom</strong> to set it to 100% (or use the keyboard shortcut: Ctrl + 0).<br><br> 

<img src="images/chrome/fig3.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br><br>

4.&nbsp; Locate the <strong>Downloads</strong> section.<br><br>

5.&nbsp; Enable <strong>Ask where to save each file before downloading</strong>.<br><br>

<img src="images/chrome/fig4.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br><br>

4.&nbsp; Locate the <strong>Privacy and security</strong> section.<br><br>

5.&nbsp; Click <strong>Content Settings</strong>.<br><br>

<img src="images/chrome/fig5.png" alt="Pop up blocker"><br><br>

6.&nbsp; Under <strong>Popups</strong> section enable <strong>Allowed</strong>.<br><br>

<img src="images/chrome/fig6.png" alt="Pop up blocker"><br><br>

<h3>Allow All Sites to Run JavaScript</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br> <br>

3.&nbsp; Scroll to the bottom and click <strong>Advanced</strong>.<br> <br>

4.&nbsp; Locate the <strong>Privacy and security</strong> section. <br> <br>

5.&nbsp; Click <strong>Content Settings</strong>.<br><br>

6.&nbsp; Under <strong>JavaScript</strong> enable <strong>Allowed</strong>.<br><br>

<img src="images/chrome/fig7.png" alt="Allow JavaScript"><br><br>

<h3>Unblock Third-Party Cookies and Site Data</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner <strong>Settings > Advanced > Privacy and security > Content Settings > Cookies </strong>.<br><br>

2.&nbsp; Enable <strong>Allow sites to save and read cookie data (recommended)</strong>.<br><br>

3.&nbsp; Disable <strong>Block third-party cookies</strong>.<br><br>

<img src="images/chrome/fig8.png" alt="Allow Cookies"><br><br>

<h3>Allow all Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on <img src="images/chrome/fig1.png" alt="chrome settings button"> in the upper right corner <strong>> Settings > Advanced > Privacy and security > Content Settings</strong>.<br> <br>

2.&nbsp; Under <strong>Automatic Downloads</strong> section enable <strong>Allow all sites to download multiple files automatically</strong> .<br><br>

<img src="images/chrome/fig9.png" alt="Automatic Download"><br><br>

<h3>Disable Web Security</h3>

<p>1. Open the Default Chrome User data folder under the your Windows account - "C:\Users\[WindowsUser]\AppData\Local\Google\Chrome\User Data\Default" and locate the <strong>Preferences</strong> file.</p><br>

<p>2. Open it with a text editor and search for "webkit". If there is no such preference in the file, add the following at the bottom of the file:</p><br>

<style>
.code {
  background-color: #FFFFFF;    
  text-align: left;
  text-indent: 50px;
  color: #000000;
}
</style>

<div class="code">
    <p>"webkit":{"webprefs":{"web_security_enabled":false}}</p>
</div>
<br>
<p>If the "webkit" preference already exists in the <strong>Preferences</strong> file and has any value in the "webprefs", you can add the web security as follows:</p>
<br>
<div class="code">
    <p>Existing values listed in the file:</p>
    <p>"webkit":{"webprefs":{"minimum_font_size":6}}</p><br>
    <p>The file after adding the web security:</p>
    <p>"webkit":{"webprefs":{"minimum_font_size":6, "web_security_enabled":false}}</p>
</div>

<hr/>

</div>
</div>
<p><hr></p>
<p></p>
<p></p>
### Microsoft Edge Chromium

You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).<br><br>

<p></p>
<p></p>
<p><hr></p>
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

<img src="images/edge-chromium/fig2.png" alt="Extensions"><br><br>

<h3>Zoom Level Set to 100%</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Use the plus (+) and minus (-) buttons next to <strong>Zoom</strong> to set it to 100%.<br><br> 

<img src="images/edge-chromium/fig3.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Downloads</strong> section.<br><br>

4.&nbsp; Enable <strong>Ask where to save each file before downloading</strong>.<br><br>

<img src="images/edge-chromium/fig4.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Pop-ups and redirects</strong> section.<br><br>

5.&nbsp; Disable the <strong>Block</strong> option.<br><br>

<img src="images/edge-chromium/fig6.png" alt="Pop up blocker"><br><br>

<h3>Allow All Sites to Run JavaScript</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>JavaScript</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allowed</strong> option.<br><br>

<img src="images/edge-chromium/fig7.png" alt="Allow JavaScript"><br><br>

<h3>Unblock Third-Party Cookies and Site Data</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Cookies and site data</strong> section.<br><br>

5.&nbsp; Enable the <strong>Allow sites to save cookies</strong> option.<br><br>

6.&nbsp; Disable the <strong>Block third-party cookies</strong> option.<br><br>

<img src="images/edge-chromium/fig8.png" alt="Allow Cookies"><br><br>

<h3>Allow all Sites to Download Multiple Files Automatically</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Settings</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Open the <strong>Automatic downloads</strong> section.<br><br>

5.&nbsp; Enable the <strong>Ask when site tries to download multiple files</strong> option.<br><br>

<img src="images/edge-chromium/fig9.png" alt="Automatic Download"><br><br>

<h3>Allow Extension from Other Stores</h3>

1.&nbsp; Click on Edge browser *Settings* button - the three dots located in the upper right corner of the browser.<br><br>

2.&nbsp; Select <strong>Extensions</strong> from the drop-down menu.<br><br>

3.&nbsp; Locate the <strong>Site Permissions</strong> section.<br><br>

4.&nbsp; Enable the <strong>Allow extensions from other stores</strong> option.<br><br>

<img src="images/edge-chromium/fig10.png" alt="Allow Extension from Other Stores"><br><br>

<hr/>

</div>
</div>

<p><hr></p>
<p></p>
<p></p>
### FireFox

You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).<br><br>

<p></p>
<p></p>
<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";> Manual Configuration <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<h3>Enable Progress Test Studio Extension</h3>

1. Click on browser settings in the right upper corner and press on <strong>Add-ons</strong>.<br><br>

<img src="images/firefox/fig1.png" alt="Extension"><br><br>

2. Ensure that the <strong>Progress Test Studio Extension</strong> is enabled.<br><br>

<img src="images/firefox/fig2.png" alt="Extension"><br><br>

<h3>Zoom Level Set to 100%</h3>

1. Click on browser settings.<br>

2. Use the plus (+) and minus (-) buttons to set it to 100%.<br><br>

<img src="images/firefox/fig3.png" alt="Zoom"><br><br>

<h3>Turn Off Pop-up Blocker & Enable JavaScript</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br><br>

<img src="images/firefox/fig4.png" alt="Zoom"><br><br>

2. Click on the <strong>Privacy and Security</strong> tab (on the left side) and scroll down to <strong>Permissions</strong> section.<br><br>

3. Uncheck the <strong>Block pop-up windows</strong> checkbox.<br><br>

<img src="images/firefox/fig5.png" alt="Pop up blocker"><br><br>

<h3>Pop-ups Open in a New Tab</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>

2. Scroll down to <strong>Tabs</strong> section and check <strong>Open new windows in a new tab instead</strong>. <br><br>

<img src="images/firefox/fig6.png" alt="Pop up open in new window"><br><br>

<h3>Enable File Downloads</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>

2. Scroll down to <strong>Downloads</strong> section and check and select <strong>Always ask you where to save files</strong>.<br><br>

<img src="images/firefox/fig7.png" alt="Downloads"><br><br>

<h3>Enable Cookies</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>Privacy and Security</strong>.<br>
3. Scroll down to <strong>History</strong> section to set the option to <strong>Remember history</strong>.<br><br>

<img src="images/firefox/fig8.png" alt="Cookies"><br><br>

<h3>Disable 'Remember passwords for sites'</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>Privacy and Security</strong>.<br>
3. Make sure the <strong>Remember logins and passwords for websites</strong> option is disabled.<br><br>

<img src="images/firefox/fig9.png" alt="Passwords"><br><br>

<h3>Use System Proxy Settings</h3>

As of the 2012 R1 version released in April 2012, set the Connection Settings to Use system proxy settings.<br><br>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>General</strong>.<br>
3. Scroll down to <strong>Network Proxy</strong> section and press on <strong>Settings... </strong> button.<br>
4. In the <strong>Connection Settings</strong> window select <strong>Use system proxy settings</strong>.<br><br>

<img src="images/firefox/fig15.png" alt="Proxy"><br><br>

<h3>Setting Configuration Flags</h3>

There are three more settings to be modified in the configuration editor -  type <strong>about:config</strong> in the url bar and press Enter to access it. Double click the following settings to set these to <strong>false</strong>:

<ul>
	<li> <strong>browser.sessionstore.resume_from_crash</strong> <br> <br> <img src="images/firefox/fig16.png" alt="browser_sessionstore_resume_from_crash"> <br> </li>
	<li> <strong>browser.tabs.warnOnClose</strong> <br> <br><img src="images/firefox/fig17.png" alt="browser_tabs_warnOnClose"> <br></li>
	<li> <strong>browser.tabs.warnOnCloseOtherTabs</strong> <br> <br> <img src="images/firefox/fig18.png" alt="browser_tabs_warnOnCloseOtherTabs"> <br></li>

</ul>

<br>

<h3>Disable Conflicting Extensions</h3>

The following Add-ons are known to conflict with the Progress Test Studio Extension: <br>

<ul>
	<li>AOL Messaging Toolbar</li>
	<li>FoxyProxyStandard</li>
</ul>

</div>
</div>
<p><hr></p>
<p></p>
<p></p>

### Safari

If you need to double check manually if all settings are correct expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.
<p></p>
<p></p>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a href="#" style="color:black; text-decoration: none;";>Manual Configuration <span id="d" style="color:#28a1e2";>+</span></a></p>

<div class="toggle_container">
<div class="block">

<h3>Zoom Level Set to 100%</h3>

1. Click the <strong>Page</strong> icon and then select <strong>Zoom</strong>.<br><br>
2. Choose <strong>Actual Size</strong> (or use the keyboard shortcut: Ctrl + 0).<br><br>

<img src="images/safari/fig1.png" alt="Zoom"><br><br>

<h3>Enable File Downloads</h3>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>General</strong> tab.<br><br>
3. Make sure that <strong>Always prompt before downloading</strong> is checked.<br><br>

<img src="images/safari/fig2.png" alt="Downloads"><br><br>

<h3>Disable Pop-up Blocker, Enable Plug-ins, Accept Cookies, Enabled JavaScript, & No Mixed Content Prompt</h3>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Security</strong> tab.<br><br>
3. Make sure that <strong>Enable JavaScript</strong> is checked.<br><br>
4. Make sure that <strong>Block pop-up windows</strong> is unchecked.<br><br>
5. Make sure <strong>Always</strong> is selected.<br><br>
6. Make sure <strong>Ask before sending a non-secure form to a secure website</strong> is unchecked.<br><br>

<img src="images/safari/fig3.png" alt="Security"><br><br>

<h3>Enable Extensions</h3>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Extensions</strong> tab.<br><br>
3. Make sure that Extensions is set to <strong>On</strong>.<br><br>
4. Make sure that the <strong>Telerik Test Studio Automation Extension</strong> extension is enabled.<br><br>

<img src="images/safari/fig4.png" alt="Extension"><br><br>

<h3>Pop-ups Open in a New Window</h3>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Tabs</strong> tab.<br><br>
3. Set <strong>Open pages in tabs instead of windows</strong> to <strong>Never</strong>.<br><br>
4. Place a check by <strong>When a new tab or window opens, make it active</strong>.<br><br>

<img src="images/safari/fig5.png" alt="Pop up"><br><br>

<h3>Never Block Cookies</h3>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Privacy</strong> tab.<br><br>
3. Under the <strong>Block cookies</strong> section, select <strong>Never</strong>.<br><br>

<img src="images/safari/fig6.png" alt="Pop up"><br><br>
</div>
</div>

<script>
window.addEventListener('DOMContentLoaded', function () {	
$(".toggle_container").hide();
    
    $("p.trigger").click(function(){
    $(this).toggleClass("active").next().slideToggle("normal");
	$(this).find('#d').text(function (i, oldText) {
    return $.trim(oldText) == '+' ? '-' : '+';
	});
		
    });
	});
</script>
