---
title: Firefox
page_title: Firefox
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/configure-your-browser/firefox.aspx, /user-guide/configure-your-browser/firefox, /getting-started/configure-your-browser/firefox
position: 1
---


<style>
p.trigger{
	margin-bottom:7px;
	margin-top:-5px;
	font-size:1.6rem;

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

# Configuring Firefox for Test Studio Automation#

To configure Mozilla Firefox for web automation in Test Studio the following steps need to be performed: <br>

## 1. Install Progress Extension

**Test Studio 2017 R3 (v. 2017.3.1010) And Later**

Install the latest Firefox extension from the Mozzila Extension Page. There is a single extension combining recording and execution: <a href="https://addons.mozilla.org/en-US/firefox/addon/progress-test-studio-extension/" target="_blank">**Progress Test Studio Extension**</a>

As of product release **2017 R3** only the new Test Studio extension will be supported. Old extensions are using legacy Firefox add-on API and starting from Firefox v.57 only extensions developed using WebExtensions APIs will be supported for usage in the browser.

Once Firefox is used for first time for web automation in Test Studio 2017 R3 the old Test Studio extensions will be automatically removed.

>If you face any troubles when installing or enabling the extension please expand the <a href="#Extension_Install">Extension Install Procedure</a> section below.

**Test Studio 2017 R2 SP1 (v. 2017.2.824) And Earlier**

The extensions get installed directly with Test Studio installation. If you need to add or reinstall these manually please visit  <a href="/troubleshooting-guide/browser-inconsistencies-tg/extensions-disabled-in-ff" target="_blank">this troubleshooting article</a>.

## 2. Browser Calibration

To ensure flawless and consistent automation process there are some settings to apply to the browser. We call this browser calibration and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box and no manual interaction is required.<br><br>

>If you need to double check manually if all settings are correct expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.<br><br>

<p></p>
<p></p>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Extension_Install" style="color:black; text-decoration: none;";> Extension Install Procedure <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

1.&nbsp; The latest Firefox extension is not automatically installed with the Test Studio installation.<br><br>
In case you haven't performed the above recommendation to install the Progress extension manually when you first start recording against Firefox the browser will load the recording start page and will try to load the extension. If that is missing the recorder will search for it for the set ClientReady Timeout (the default is 60 seconds).<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig14.png" alt="Wait For Extension"><br><br>

2.&nbsp; In case the Progress extension is not yet loaded after that timeout a link to the Mozzila Extension Page will be displayed to install the extension.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig10.png" alt="Get Extension"><br><br>

3.&nbsp; By clicking on <strong>Get It Free From Mozilla Extensions Page</strong> you will be directly navigated to the Progress extension on the Extension Page.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig11.png" alt="Extension In Page"><br><br>

4.&nbsp; By clicking the <strong>Add to Firefox</strong> button the extension will be added after confirmation. <br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig12.png" alt="Add Extension Confirmation"><br><br>

5.&nbsp;  The version of an installed extension could be double checked by clicking on its icon located on the right of the address bar.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig13.png" alt="Extension Version"><br><br>

<hr/>

</div>
</div>

<p></p>
<p></p>
<p></p>

<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";> Manual Configuration <span id="d" style="color:#28a1e2";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<h3>Enable Progress Test Studio Extension</h3>

1. Click on browser settings in the right upper corner and press on <strong>Add-ons</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig1.png" alt="Extension"><br><br>

2. Ensure that the <strong>Progress Test Studio Extension</strong> is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig2.png" alt="Extension"><br><br>

<h3>Zoom Level Set to 100%</h3>

1. Click on browser settings.<br>

2. Use the plus (+) and minus (-) buttons to set it to 100%.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig3.png" alt="Zoom"><br><br>

<h3>Turn Off Pop-up Blocker & Enable JavaScript</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig4.png" alt="Zoom"><br><br>

2. Click on the <strong>Privacy and Security</strong> tab (on the left side) and scroll down to <strong>Permissions</strong> section.<br><br>

3. Uncheck the <strong>Block pop-up windows</strong> checkbox.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig5.png" alt="Pop up blocker"><br><br>

<h3>Pop-ups Open in a New Tab</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>

2. Scroll down to <strong>Tabs</strong> section and check <strong>Open new windows in a new tab instead</strong>. <br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig6.png" alt="Pop up open in new window"><br><br>

<h3>Enable File Downloads</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>

2. Scroll down to <strong>Downloads</strong> section and check and select <strong>Always ask you where to save files</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig7.png" alt="Downloads"><br><br>

<h3>Enable Cookies</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>Privacy and Security</strong>.<br>
3. Scroll down to <strong>History</strong> section to set the option to <strong>Remember history</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig8.png" alt="Cookies"><br><br>

<h3>Disable 'Remember passwords for sites'</h3>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>Privacy and Security</strong>.<br>
3. Make sure the <strong>Remember logins and passwords for websites</strong> option is disabled.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig9.png" alt="Passwords"><br><br>

<h3>Use System Proxy Settings</h3>

As of the 2012 R1 version released in April 2012, set the Connection Settings to Use system proxy settings.<br><br>

1. Click on browser settings and press on <strong>Options</strong>.<br>
2. Click on the <strong>General</strong>.<br>
3. Scroll down to <strong>Network Proxy</strong> section and press on <strong>Settings... </strong> button.<br>
4. In the <strong>Connection Settings</strong> window select <strong>Use system proxy settings</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/firefox/fig15.png" alt="Proxy"><br><br>

<h3>Setting Configuration Flags</h3>

There are three more settings to be modified in the configuration editor -  type <strong>about:config</strong> in the url bar and press Enter to access it. Double click the following settings to set these to <strong>false</strong>:

<ul>
	<li> <strong>browser.sessionstore.resume_from_crash</strong> <br> <br> <img src="/img/general-information/configure-your-browser/firefox/fig16.png" alt="browser_sessionstore_resume_from_crash"> <br> </li>
	<li> <strong>browser.tabs.warnOnClose</strong> <br> <br><img src="/img/general-information/configure-your-browser/firefox/fig17.png" alt="browser_tabs_warnOnClose"> <br></li>
	<li> <strong>browser.tabs.warnOnCloseOtherTabs</strong> <br> <br> <img src="/img/general-information/configure-your-browser/firefox/fig18.png" alt="browser_tabs_warnOnCloseOtherTabs"> <br></li>

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

<script>
$(".toggle_container").hide();
    
    $("p.trigger").click(function(){
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
</script>