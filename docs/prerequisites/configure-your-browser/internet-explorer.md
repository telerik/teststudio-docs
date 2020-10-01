---
title: Internet Explorer
page_title: Internet Explorer
description: "Configure IE to use for testing with Test Studio. Prerequisites for testing against Internet Explorer with Test Studio. "
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

# Configuring Internet Explorer for Test Studio Automation #

To configure Microsoft Internet Explorer for web automation with Test Studio, there are certain settings required. Complete the following steps to adjust the browser for test recording and execution.

## Automatic Calibration ##

To ensure flawless and consistent automation process there are some settings to apply to the browser. We call this browser calibration and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box and no manual interaction is required.<br><br>

**Note:** If you receive a certificate-related warning when the <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> recorder is attached to the browser, or when executing a Performance run, follow the instructions <a href="/knowledge-base/project-configuration-kb/register-certificate" target="_blank">here</a>. 

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

1. Go to the higher right of the browser.<br><br>
2. Click Tools button -> <strong>Zoom</strong>.<br><br>
3. Select 100% (or use the keyboard shortcut: Ctrl + 0).<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig1.png" alt="Zoom"><br><br>

<h2>Disable Protected Mode</h2>

1. Click <strong>Tools > Internet Options</strong>. <br><br> 
2. Click the <strong>Security</strong> tab.<br><br>
3. Uncheck the <strong>Enable Protected Mode</strong> checkbox.<br><br>
4. Repeat step 3 for:<br><br>
- <strong>Internet</strong><br><br>
- <strong>Local intranet</strong><br><br>
- <strong>Trusted sites</strong><br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig2.png" alt="Protected Mode"><br><br>


<h2>Disable Pop-up Blocker</h2>

1. Click <strong>Tools > Internet Options</strong><br><br>
2. Click the <strong>Privacy</strong> tab.<br><br>
3. Uncheck the <strong>Turn on Pop-up Blocker</strong> checkbox.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig3.png" alt="Pop up blocker"><br><br>

<h2>Pop-ups Open in a New Window</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. On the <strong>General tab</strong>, click the <strong>Settings</strong> button for </strong>Change how webpages are displayed in tabs</strong>.<br><br>
3. Select <strong>Always open pop-ups in a new window</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig4.png" alt="Pop ups open in new window"><br><br>

<h2>Add the Websites to List of Trusted Sites</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click on <strong>Trusted sites</strong>.<br><br>
4. Click the <strong>Sites</strong> button.<br><br>
5. If your site is not secure (uses HTTPS protocol), then uncheck the <strong>Require server verification</strong>... checkbox.<br><br>
6. Enter the URL of your website in <strong>Add this website to the zone</strong> text box. This text box will accept both DNS names and IP addresses.<br><br>
7. Click <strong>Add</strong>.<br><br>
8. Repeat steps 6-7 for each website you'll be testing.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig5.png" alt="Trusted site"><br><br>

<h2>Disable Trusted Sites Message</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>.<br><br>
4. Scroll down until you find the <strong>Websites in less privileged web content zone</strong> can navigate into this zone under the <strong>Miscellaneous heading</strong>.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig6.png" alt="Trusted site message"><br><br>

<h2>Ensure JavaScript Is Enabled</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>Active scripting</strong> setting under the <strong>Scripting</strong> heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig7.png" alt="Enable Scripting"><br><br>

<h2>Disable Mixed Content Message</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>Display mixed content</strong> setting under the Micellaneous heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig8.png" alt="Disable script content"><br><br>

<h2>Enable File Downloads</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong> and then <strong>Custom level</strong>. <br><br>
4. Scroll down until you find the <strong>File download</strong> setting under the Downloads heading.<br><br>
5. Check <strong>Enable</strong>.<br><br>
6.  Repeat steps 3 - 5 for the <strong>Local intranet</strong> and the <strong>Internet</strong> zones.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig9.png" alt="Downloads"><br><br>

For <strong>IE7</strong> and <strong>IE8</strong> file downloads, uncheck <strong>Close this dialog box when download completes</strong>. The only way to do this is to actually start downloading something and uncheck this checkbox while the download is running.<br><br>
	
<img src="/img/general-information/configure-your-browser/internet-explorer/fig10.png" alt="Downloads"><br><br>

For <strong>IE9</strong> downloads, check <strong>Notify me when my downloads are complete</strong>:<br><br>

1. Click <strong>Tools > View downloads</strong>.<br><br>
2. Click the <strong>Options</strong> link in the lower left.<br><br>
3. Check <strong>Notify me when my downloads are complete</strong>.<br><br>
4. Click <strong>OK</strong><br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig11.png" alt="Downloads"><br><br>

<h2>Allow Local Files to Run Unhindered</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Advanced</strong> tab.<br><br>
3. Check <strong>Allow active content to run in files on My Computer</strong> under the <strong>Security</strong> heading.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig12.png" alt="Local files"><br><br>

<h2>Turn Off AutoComplete</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Content</strong> tab.<br><br>
3. Click the <strong>Settings</strong> button under the <strong>AutoComplete</strong> section.<br><br>
4. In <strong>AutoComplete Settings</strong>, uncheck <strong>Forms</strong> and <strong>User names and passwords on forms</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig13.png" alt="Turn of auto-complete"><br><br>

<h2>Windows updates</h2>

The latest Internet Explorer updates should be installed. <br><br>

<strong>Note:</strong> Installing <a href="http://www.microsoft.com/en-us/download/details.aspx?id=44431" target="_blank">KB2987107</a> security update for Internet Explorer 11 helps some customers with recording issues.<br><br>

<h2>Add http://www.w3.org to Trusted Sites</h2>

1. Click <strong>Tools > Internet Options</strong>.<br><br>
2. Click the <strong>Security</strong> tab.<br><br>
3. Click <strong>Trusted sites</strong>.<br><br>
4. Add <strong>http://www.w3.org</strong> to the trusted sites.<br><br>

<img src="/img/general-information/configure-your-browser/internet-explorer/fig14.png" alt="Add http://www.w3.org"><br><br>

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