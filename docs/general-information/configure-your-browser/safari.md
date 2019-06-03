---
title: Safari
page_title: Safari
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/configure-your-browser/safari.aspx, /user-guide/configure-your-browser/safari.aspx, /getting-started/configure-your-browser/safari
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

# Configuring Safari for Test Studio Automation#

## Automatic Calibration##

The <a href="/features/project-settings/browsers" target="_blank">**Calibrate Browsers**</a> feature can configure your browsers **automatically**. 

If you need to resort to manual configuration, use the following settings:

<p class="trigger"><a href="#" style="color:black; text-decoration: none;";>Manual Configuration <span id="d" style="color:#28a1e2";>+</span></a></p>

<div class="toggle_container">
<div class="block">

<h2>Zoom Level Set to 100%</h2>

1. Click the <strong>Page</strong> icon and then select <strong>Zoom</strong>.<br><br>
2. Choose <strong>Actual Size</strong> (or use the keyboard shortcut: Ctrl + 0).<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig1.png" alt="Zoom"><br><br>

<h2>Enable File Downloads</h2>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>General</strong> tab.<br><br>
3. Make sure that <strong>Always prompt before downloading</strong> is checked.<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig2.png" alt="Downloads"><br><br>

<h2>Disable Pop-up Blocker, Enable Plug-ins, Accept Cookies, Enabled JavaScript, & No Mixed Content Prompt</h2>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Security</strong> tab.<br><br>
3. Make sure that <strong>Enable JavaScript</strong> is checked.<br><br>
4. Make sure that <strong>Block pop-up windows</strong> is unchecked.<br><br>
5. Make sure <strong>Always</strong> is selected.<br><br>
6. Make sure <strong>Ask before sending a non-secure form to a secure website</strong> is unchecked.<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig3.png" alt="Security"><br><br>

<h2>Enable Extensions</h2>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Extensions</strong> tab.<br><br>
3. Make sure that Extensions is set to <strong>On</strong>.<br><br>
4. Make sure that the <strong>Telerik Test Studio Automation Extension</strong> extension is enabled.<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig4.png" alt="Extension"><br><br>

<h2>Pop-ups Open in a New Window</h2>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Tabs</strong> tab.<br><br>
3. Set <strong>Open pages in tabs instead of windows</strong> to <strong>Never</strong>.<br><br>
4. Place a check by <strong>When a new tab or window opens, make it active</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig5.png" alt="Pop up"><br><br>

<h2>Never Block Cookies</h2>

1. Click the <strong>Tools</strong> icon and then select <strong>Preferences</strong> from the drop-down menu.<br><br>
2. Click on the <strong>Privacy</strong> tab.<br><br>
3. Under the <strong>Block cookies</strong> section, select <strong>Never</strong>.<br><br>

<img src="/img/general-information/configure-your-browser/safari/fig6.png" alt="Pop up"><br><br>


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