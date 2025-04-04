---
title: Firefox
page_title: Firefox
description: "Configure Firefox to use for testing with Test Studio. Prerequisites for testing against Firefox with Test Studio. Firefox extension not found."
position: 3
---


<style>
.code {
  background-color: #FFFFFF;
  text-align: left;
  text-indent: 50px;
  color: #000000;
}
</style>

# Configuring Firefox for Test Studio Automation

This document describes the steps to enable Firefox browser for test recording and execution.

## 1. Install the Progress Extension

Install the latest <a href="https://addons.mozilla.org/en-US/firefox/addon/progress-test-studio-extension/" target="_blank">**Progress Test Studio Extension**</a></a> from the Firefox Add-Ons store.

> __Important__
> <br>
> <br>
> If you face any troubles when installing or enabling the extensions, expand the <a href="#Extension_Install">Extension Install Procedure</a> section below.

## 2. Browser Calibration

To ensure a flawless and consistent automation process, there are a few browser settings that we need to apply. We call this **browser calibration** and have implemented a feature to <a href="/features/project-settings/browsers" target="_blank">**automatically calibrate the browser**</a> out of the box. No manual interaction is required.

> __Tip__
> <br>
> <br>
> You can check all settings applied from the calibration in the <a href="#Manual_Configuration">Manual Configuration</a> section below (click the + sign to expand it).


## Extension Install Procedure

1.&nbsp; When you start recording against Firefox, but the Progress extension is not installed, the browser will load the recording start page and will try to load the extension. The recorder will search for the extension for the period that is defined in the *ClientReady* Timeout (the default is 60 seconds).

<img src="/img/general-information/configure-your-browser/firefox/fig14.png" alt="Wait For Extension">

2.&nbsp;  If the Progress extension doesn't load within the timeout period, a link to the Mozzila Extension Page will be displayed to install the extension.

<img src="/img/general-information/configure-your-browser/firefox/fig10.png" alt="Get Extension">

3.&nbsp; By clicking on <strong>Get It Free From Mozilla Extensions Page</strong> you will be directly navigated to the Progress extension on the Extension Page.

<img src="/img/general-information/configure-your-browser/firefox/fig11.png" alt="Extension In Page">

4.&nbsp; By clicking the <strong>Add to Firefox</strong> button the extension will be added after confirmation. 

<img src="/img/general-information/configure-your-browser/firefox/fig12.png" alt="Add Extension Confirmation">

5.&nbsp; Click on the icon located to the right of the address bar to find the extension's version.

<img src="/img/general-information/configure-your-browser/firefox/fig13.png" alt="Extension Version">

## Manual Configuration

### Enable Progress Test Studio Extension

Follow the steps below to manually configure Firefox for web automation with Test Studio.

1. Click on the browser settings button in the upper right corner and select <strong>Add-ons</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig1.png" alt="Extension">

2. Ensure that the <strong>Progress Test Studio Extension</strong> is enabled.

<img src="/img/general-information/configure-your-browser/firefox/fig2.png" alt="Extension">

### Zoom Level Set to 100%

1. Click on the browser settings button.<br>

2. Use the plus (+) and minus (-) buttons to set it to 100%.

<img src="/img/general-information/configure-your-browser/firefox/fig3.png" alt="Zoom">

### Turn Off Pop-up Blocker & Enable JavaScript

1. Click on the browser settings button and select <strong>Options</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig4.png" alt="Zoom">

2. Click on the <strong>Privacy and Security</strong> tab (on the left side) and scroll down to <strong>Permissions</strong> section.

3. Uncheck the <strong>Block pop-up windows</strong> checkbox.

<img src="/img/general-information/configure-your-browser/firefox/fig5.png" alt="Pop up blocker">

### Pop-ups Open in a New Tab

1. Click on the browser settings button and select <strong>Options</strong>.<br>

2. Scroll down to the <strong>Tabs</strong> section and check <strong>Open new windows in a new tab instead</strong>. 

<img src="/img/general-information/configure-your-browser/firefox/fig6.png" alt="Pop up open in new window">

### Enable File Downloads

1. Click on the browser settings button and select <strong>Options</strong>.<br>

2. Scroll down to the <strong>Downloads</strong> section and check and select <strong>Always ask you where to save files</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig7.png" alt="Downloads">

### Enable Cookies

1. Click on the browser settings button and select <strong>Options</strong>.<br>
2. Click on <strong>Privacy and Security</strong>.<br>
3. Scroll down to the <strong>History</strong> section to set the option to <strong>Remember history</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig8.png" alt="Cookies">

### Disable 'Remember passwords for sites'

1. Click on the browser settings button and select <strong>Options</strong>.<br>
2. Click on <strong>Privacy and Security</strong>.<br>
3. Make sure the <strong>Remember logins and passwords for websites</strong> option is disabled.

<img src="/img/general-information/configure-your-browser/firefox/fig9.png" alt="Passwords">

### Set PDF Files to Be Always Saved

1. Click on the browser settings button and select <strong>Options</strong>.<br>
2. Locate the <strong>Applications</strong> section on the <strong>General Settings tab</strong>.<br>
3. Set the PDF format file action to <strong>Save File</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig20.png" alt="Save PDF file">

### Use System Proxy Settings

As of the 2012 R1 version released in April 2012, set the Connection Settings to Use system proxy settings.

1. Click on the browser settings button and select <strong>Options</strong>.<br>
2. Click on <strong>General</strong>.<br>
3. Scroll down to the <strong>Network Proxy</strong> section and press on <strong>Settings... </strong> button.<br>
4. In the <strong>Connection Settings</strong> window select <strong>Use system proxy settings</strong>.

<img src="/img/general-information/configure-your-browser/firefox/fig15.png" alt="Proxy">

### Setting Configuration Flags

There are three more settings to be modified in the configuration editor -  type <strong>about:config</strong> in the url bar and press Enter to access it. Double click the following settings to set these to <strong>false</strong>:

- **browser.sessionstore.resume_from_crash**
<img src="/img/general-information/configure-your-browser/firefox/fig16.png" alt="browser_sessionstore_resume_from_crash">

- **browser.tabs.warnOnClose**
<img src="/img/general-information/configure-your-browser/firefox/fig17.png" alt="browser_tabs_warnOnClose">

- **browser.tabs.warnOnCloseOtherTabs**
<img src="/img/general-information/configure-your-browser/firefox/fig18.png" alt="browser_tabs_warnOnCloseOtherTabs">

### Disable Conflicting Extensions

The following Add-ons are known to conflict with the Progress Test Studio Extension: <br>

- AOL Messaging Toolbar
- FoxyProxyStandard