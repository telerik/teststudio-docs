---
title: Silverlight Unable to Connect
page_title: Unable to Connect to Silverlight Application 
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/troubleshooting_guide/recording-problems/unable-to-connect-to-silverlight-application.aspx, /user-guide/troubleshooting_guide/recording-problems/unable-to-connect-to-silverlight-application
position: 1
published: false
---
# Unable to Connect to Silverlight Application 

## PROBLEM

 You cannot record your Silverlight application through Test Studio and receive an "Unable to connect" error message. 

## KNOWN ISSUES

- **The MIME Type for your XAP file is not properly registered on your web server. This is the most common cause for this type of issue.**

- Automation only supports .XAP Silverlight app deployment (the .NET method). 

> .XBAP or Javascript Silverlight deployment is not supported.

## SOLUTION

1.&nbsp; Make sure that you have registered the .XAP file extension within IIS. These instructions are also documented <a href="http://learn.iis.net/page.aspx/262/configuring-iis-for-silverlight-applications/" target="blank">**here**</a>.


 a. Click **Start** > **Run** (XP) or **Start** then click in the search field (Vista/Win7/Win8).
 b. Type *IIS* within the search/run field.
 c. Hit 'Enter' on your keyboard.
 d. Make sure you are targeting the "Default Web Site" in the left column.
 e. Double-click *MIME Types* in Features View.
 f. Click **Add** (right column).
 g. Set the file extension to **.XAP**.
 h. Set the MIME Type to *application/x-silverlight-app*
 i. Click OK.

2.&nbsp; If the Web and Silverlight app is deployed locally, try adding a period ('.') after localhost, as in http://localhost.: 

3.&nbsp; Delete the entire cache for the test playback browser: 


 a. In Interent Explorer, select: **Tools > Internet Options > General Tab > Delete (Within the browsing history section)**

 b. In Firefox, select: **Tools > Clear Recent History > Select Everything in the 'Time Range to Clear' drop-down menu > Choose Clear Now**

 c. In Safari, select: **Settings (the gear in the upper-right of the Safari window) > Reset Safari > Check only Empty the Cache > Click Reset**

 d. In Chrome, select: **Tools menu > Options > Click the Under the Hood tab > Click Clear browsing data...**


4.&nbsp; <a href="http://support.microsoft.com/kb/923737" target="_blank">Reset Internet Explorer settings</a>.

5.&nbsp; Try increasing the (Settings.) <a href="/features/project-settings/recording-options" target="_blank">Silverlight Connect Timeout</a> if the Silverlight app has a longer load time. 

6.&nbsp; Try setting externalAccessfromCrossDomainCallers to script only your application's AppManifest.xaml file by doing the following in your html page and Silverlight manifest: 

 a. **Example for html page:**


	<div id="silverlightControlHost" />
	<object height="300" width="300" type="application/x-silverlight-2" data="data:application/x-silverlight-2," >
	<param value="http://a-remote-domain.com/ClientBin/SilverlightClient.xap" name="source" />
	<param value="white" name="background" />
	<param value="3.0.40723.0" name="minRuntimeVersion" />
	<param value="true" name="enableHtmlAccess" />
	<param value="visOnly=true" name="initParams" />
	<a style="text-decoration: none;" href="http://go.microsoft.com/fwlink/?LinkID=149156">
	<img style="border-style: none; width: 400px; height: 200px;" alt="Install Microsoft Silverlight" src="http://storage.timheuer.com/sl4wp-ph.png"/></a></object>
	<iframe style="border: 0px none ; visibility: hidden; height: 0pt; width: 0pt;" /></div>

 b. **Example for SL Manifest:** 


	<Deployment xmlns="http://schemas.microsoft.com/client/2007/deployment" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" ExternalCallersFromCrossDomain="ScriptableOnly">
	<Deployment.Parts>
	</Deployment.Parts>
	</Deployment>

> See <a href="https://social.msdn.microsoft.com/Forums/silverlight/en-us/home?category=silverlight" target="_blank">this Microsoft forum thread</a> for more information

7.&nbsp; Try setting the "windowless" property for your Silverlight app to "true":

Example (similar to first example above):


	<object id="xamlHost0" width="900" height="412" type="application/x-silverlight">
	<param value="transparent" name="background"/>
	<param value="true" name="windowless"/>
	<!-- a bunch of other params go here -->
	</object>

8.&nbsp; Check the headers your server is sending for the Silverlight Page by: 


 a. Install/Run <a href="http://www.telerik.com/fiddler" target="_blank">Fiddler</a> and load your Silverlight page.
 
 b. Click the response for the .xap file
 
 c. Click **Inspectors > Headers**.
 
 There should be an entry titled: Content:*application/x-silverlight-app*
 This must be in response in order for the Telerik Testing Framework or Test Studio to detect the Silverlight app.

