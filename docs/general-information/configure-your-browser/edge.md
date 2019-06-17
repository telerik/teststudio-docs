---
title: MS Edge
page_title: MS Edge
description: Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing.
publish: true
position: 1
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

# Configuring MS Edge for Test Studio Automation#

## 1. Install Microsofot WebDriver

In order to use **Edge** browser for Test Studio automation you need to install **Microsoft WebDriver**. Depending on your Windows 10 build you should choose the correct WebDriver. 

Determine your Windows 10 build and download the correct MS WebDriver <a href="https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/" target="_blank">here</a>.

### Windows 10 Anniversary Update (build 14393) And Later

>**Note:** The following steps apply for Windows 10 **Anniversary Update (build 14393)** and later. If you don't use it skip to the <a href="#Automatic-Calibration">Automatic Calibration</a> step.

Microsoft WebDriver for that build doesn't include installer (\*.msi) but only \*.exe file. You should manually locate the WebDriver exe file in the Test Studio project settings.

### Install On Local Machine

1.1 &nbsp; Download Microsoft WebDriver for release 14393 from <a href="https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/" target="_blank">here</a> and save it on your computer.

1.2 &nbsp; Locate WebDriver from the **Project Settings -> Browsers**

![Locate WebDriver][6]

1.3 &nbsp; Navigate to the download location and select WebDriver exe file.

![Locate WebDriver Folder][7]

1.4 &nbsp; The location of WebDriver is now successful

![Locate WebDriver successful][8]

### Install On Remote Machine

2.&nbsp; Executing tests against Edge browser on a remote machine also requires to set the path to the WebDriver.

2.1. &nbsp; Open regedit and navigate to **HKEY_LOCAL_MACHINE\Software\WOW6432Node\Telerik\TestStudio** and create a new reg key of type string.

![Regedit][9]

2.2. &nbsp; Name it **WebDriverFilePath** and as its value type the full path to the MicrosofWebDriver.exe download location. 

![WebDriverFilePath key][10]

## 2. Automatic Calibration##

To ensure flawless and consistent automation process there are some settings to apply to the browser. We call this browser calibration and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box and no manual interaction is required.<br><br>

>If you need to double check manually if all settings are correct expand the <a href="#Manual_Configuration">Manual Configuration</a> section below.

<p></p>
<p></p>

<p><hr></p>
<p></p>
<p></p>

<p class="trigger"><a name="Manual_Configuration" style="color:black; text-decoration: none;";>Manual Configuration <span id="d" style="color:#28a1e2";>+</span></a></p>

<div class="toggle_container">
<div class="block">

<h2>Zoom Level Set to 100%</h2>

1.&nbsp; Go to the higher right of the browser and click on the <strong>3 dots button</strong>.<br><br>

2.&nbsp; Select 100% zoom (or use the keyboard shortcut: Ctrl + 0).<br><br>

<img src="/img/general-information/configure-your-browser/edge/fig1.png" alt="favourites bar"><br><br>

<h2>Hide The Favorites Bar</h2>

This bar conflicts with highlighting coordinates.<br><br>

1.&nbsp; Go to the higher right of the browser and click on the <strong>3 dots button</strong>.<br><br>

2.&nbsp; Click <strong>Settings</strong> and then <strong>View favorite settings</strong>.<br><br>

3.&nbsp; Set <strong>Show the favorites bar</strong> to <strong>Off</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge/fig2.png" alt="zoom">

<h2>Open New Tabs With A Blank Page</h2>

1.&nbsp; Go to the higher right of the browser and click on the <strong>3 dots button</strong>.<br><br>

2.&nbsp; Click <strong>Settings</strong>.<br></br>

3.&nbsp; Set <strong>Open new tabs with</strong> to <strong>A blank page</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge/fig3.png" alt="new tab">

<h2>Disable Password Save Offering</h2>

1.&nbsp; Go to the higher right of the browser and click on the <strong>3 dots button</strong>.<br><br>

2.&nbsp; Click <strong>Settings</strong> and then <strong>View advanced settings</strong>.<br><br>

3.&nbsp; Set <strong>Offer to save passwords</strong> and <strong>Save for entries</strong> to <strong>Off</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge/fig4.png" alt="disable password offering">

<h2>Allow Cookies</h2>

1.&nbsp; Go to the higher right of the browser and click on the <strong>3 dots button</strong>.<br><br>

2.&nbsp; Click <strong>Settings</strong> and then <strong>View advance settings</strong>.<br><br>

3.&nbsp; Set <strong>Cookies</strong> to <strong>Don't block cookies</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/edge/fig5.png" alt="allow cookies">

</div>
</div>



<script>
$(".toggle_container").hide();
    
    $("p.trigger").click(function(){
        $(this).toggleClass("active").next().slideToggle("normal");
		$('#page-article').animate({
    		scrollTop: $('#page-article').get(0).scrollHeight
		}, 1500);
		 $(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
</script>

[1]: /img/general-information/configure-your-browser/edge/fig1.png
[2]: /img/general-information/configure-your-browser/edge/fig2.png
[3]: /img/general-information/configure-your-browser/edge/fig3.png
[4]: /img/general-information/configure-your-browser/edge/fig4.png
[5]: /img/general-information/configure-your-browser/edge/fig5.png
[6]: /img/general-information/configure-your-browser/edge/fig6.png
[7]: /img/general-information/configure-your-browser/edge/fig7.png
[8]: /img/general-information/configure-your-browser/edge/fig8.png
[9]: /img/general-information/configure-your-browser/edge/fig9.png
[10]: /img/general-information/configure-your-browser/edge/fig10.png


