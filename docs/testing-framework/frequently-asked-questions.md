---
title: Frequently Asked Questions
page_title: Frequently Asked Questions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Frequently Asked Questions#

* **How much does Telerik Testing Framework cost?**
	
*There is no fee associated with the individual Telerik Testing Framework license. If you have more than ten (10) Framework Users within your company, you must purchase a <a href="http://www.telerik.com/purchase/configure-purchase?skuId=589" target="_blank">edicated technical support package</a>d for each Framework User to be within the EULA. Read more on the rights and liabilities that the Telerik Testing Framework license grants you <a href="http://www.telerik.com/purchase/license-agreement/testing-framework-lw-s" target="_blank">here</a>*

* **Are there plans to make it open source?**
	
*Not currently.*

* **Is 64-bit Windows supported?**
	
*Yes.*
* **Do you offer any record/replay test automation tools?**
	
*Yes! Check out our <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> product.*

* **Can I use the framework without using NUnit or Visual Studio Team Test?**
	
*Yes. Use it simply within a Windows Forms application, a Console application, or a Dynamic library (.dll file). Please refer to the <a href="/testing-framework/getting-started" target="_blank">Getting Started Guide</a>.*

* **Can I use the framework for automation if I don't want to use TestRegions or inject testregion tags in my source code?**
	
*Yes. Whether or not you choose to use TestRegions, you can still use Telerik Testing Framework to automate your web application. All features will work with or without TestRegions. TestRegions is a new method that we are promoting to enable customers to design testability into their applications and help them build resilient test automation that has low maintenance cost.*

* **Can I use the framework to control my Web Server?**
	
*No. Currently no APIs are provided to control your web server (i.e. start/stop IIS).*

* **I have a test that opens a popup window. It runs just fine under IE but when I try to run it under Firefox the Manager.WaitForNewBrowserConnect call times out and throws an exception like this:**
	
System.OperationCanceledException: Exception occured waiting for the new browser to connect. --->  System.TimeoutException: Timed out waiting for the browser with url='detail' to connect..  at ArtOfTest.WebAii.Core.Manager.WaitForNewBrowserConnect(String url, Boolean isPartial, Int32 timeout)

	
Firefox needs a little help finding and connecting to the manager object. Modify your code to resemble this:

**Manager.SetNewBrowserTracking(true);**

Manager.WaitForNewBrowserConnect("detail", true, 30000);

**Manager.SetNewBrowserTracking(false);**

* **I am having some trouble getting my app.config file to work. When I try to execute a test that includes an app.config file I get an exception that looks like this:**

System.Configuration.ConfigurationErrorsException: System.Configuration.ConfigurationErrorsException: An error occurred creating the configuration section handler for WebAii.Settings: Could not load file or assembly 'ArtOfTest.WebAii, Version=X.X.XXX.X, Culture=neutral, PublicKeyToken=4fd5f65be123776c' or one of its dependencies.

*This kind of error is caused by a version mismatch between the information stored in the app.config file and the framework version you actually have installed. This happens most often right after you upgrade to a new version and you previously had tests working with an app.config file. The attributes shown in bold above is where the mismatch has occurred. You will need to update. To determine the correct values follow this procedure:*

1. Open a Visual Studio Command Prompt window.

2. Type: gacutil /l artoftest.webaii.

3. You should get a response like this: artoftest.webaii, Version=X.X.X.X, Culture=neutral, PublicKeyToken=4fd5f65be123776c, processorArchitecture=MSIL.

4. Copy the Version number and the PublicKeyToken values to the appropriate places in your app.config file like this: <section name="WebAii.Settings" type="ArtOfTest.WebAii.Core.SettingsConfigSectionHandler,ArtOfTest.WebAii, Version=X.X.X.X, Culture=neutral, PublicKeyToken=4fd5f65be123776c"/>

* **How do I send something with the Ctl or Alt keys e.g. Ctl/p, Alt/x, Alt/F4?**

*The Keyboard.KeyPress function keystroke combinations as described: <a href="http://msdn.microsoft.com/en-us/library/system.windows.forms.keys.aspx" target="_blank">here</a>. For example, to send Ctl/P use Desktop.Keyboard.Keypress(Keys.Control | Keys.P)*

* **When I try to access the .TextContent of an HtmlControl I get nothing but an empty string, yet I can see actual text in the browser window?**

*There is a significant difference between TextContent and InnerText. TextContent is only the text at the same level as the node. InnerText is the combined text from the current node and everything below it. The text you are seeing in the browser window is probably contained within another element, such as a <span> element. Studying an HTML example will help make this clear:*
	
```HTML
<td id="gridEvents_rc_0_0">
   Same Level Text
   <nobr>Foremen
       <div>Lower Level Text</div>
   </nobr>
</td>
```   

*In this example TextContent is the string "Same Level Text". InnerText is the string "Same Level TextForemenLower Level Text". You can probably use InnerText in your code in place of TextContent and be just fine.*	