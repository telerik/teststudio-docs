---
title: App .config file
page_title: App .config file
description: "Test Studio Testing Framework App .config file"
previous_url: /user-guide/write-tests-in-code/intermediate-topics/settings-and-configuration/using-application-config-file.aspx, /user-guide/write-tests-in-code/intermediate-topics/settings-and-configuration/using-application-config-file
position: 1
---
#Using the Application's .config File#

Instead of programmatically setting the configuration, the application or test program can use an application .config file to fetch the appropriate settings. The Telerik infrastructure has a built in .NET Config SectionHandler (under the 'ArtOfTest.Core' namespace) that can read the configuration settings from the .config file associated with the application or test. You place the settings in your .config file as follows:

1.&nbsp; First add the following line to the 'configSections' section:

```XML
<configSections>                                     
<section name="WebAii.Settings" type="ArtOfTest.WebAii.Core.SettingsConfigSectionHandler,ArtOfTest.WebAii"/>
<section name="WebAii.Settings.Web" type="ArtOfTest.WebAii.Core.WebSettingsConfigSectionHandler,ArtOfTest.WebAii"/>
<section type="ArtOfTest.WebAii.Core.WpfSettingsConfigSectionHandler,ArtOfTest.WebAii" name="WebAii.Settings.Wpf"/>  
</configSections>
```

2.&nbsp; Then add the settings you need under the 'WebAii.Settings' section or WebAii.Settings.Web' section.

	**Note:** It is not necessary to include all of Telerik's settings in your .config file. You only need to add settings for those you wish to override. The Telerik Testing Framework uses default values for any setting not explicitly set in the .config file. 

	**Note:** The configuration setting names are case sensitive e.g.  **AnnotateExecution** will not be recognized and will cause an exception to be thrown while **annotateExecution** will be recognized and used.

		
```XML
	<WebAii.Settings                                           
                   logLocation="F:\Log\"
                   executionTimeout="30000"
                   clientReadyTimeout="20000"                    
                   queryEventLogErrorsOnExit="false"                     
                   executionDelay="0"
                   annotateExecution="true"
                   annotationMode="All"
                   logAnnotations="false"                                              
                   waitCheckInterval="633"      
                   createLogFile="true">
	</WebAii.Settings>
	<WebAii.Settings.Web baseUrl="http://www.lava.com">           
	</WebAii.Settings.Web>
```

Here is an example of a complete app.config file that contains all of Telerik's configuration settings:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
 <configSections>
 <section type="ArtOfTest.WebAii.Core.SettingsConfigSectionHandler,ArtOfTest.WebAii" name="WebAii.Settings"/>
 <section type="ArtOfTest.WebAii.Core.WebSettingsConfigSectionHandler,ArtOfTest.WebAii" name="WebAii.Settings.Web"/>
<section type="ArtOfTest.WebAii.Core.WpfSettingsConfigSectionHandler,ArtOfTest.WebAii" name="WebAii.Settings.Wpf"/>
 </configSections>
 <WebAii.Settings elementWaitTimeout="10000" xMultiMgr="false" unexpectedDialogAction="HandleAndFailTest" createLogFile="true" waitCheckInterval="500" logAnnotations="false" annotationMode="All" annotateExecution="true" executionDelay="0" queryEventLogErrorsOnExit="false" clientReadyTimeout="20000" executionTimeout="30000" logLocation="F:\Log\"></WebAii.Settings>
 <WebAii.Settings.Web verboseHttpProxy="false" enableSilverlight="true" useHttpProxy="false" enableUILessRequestViewing="false" aspNetDevServerPort="-1" webAppPhysicalPath="" localWebServer="None" silverlightApplicationPath="" silverlightConnectTimeout="30000" enableScriptLogging="false" defaultBrowser="InternetExplorer" killBrowserProcessOnClose="false" baseUrl="http://www.telerik.com"> </WebAii.Settings.Web>
<WebAii.Settings.Wpf defaultApplicationPath="E:\Users\Dad\Documents\visual studio 2010\Projects\TelerikWpfApp1\TelerikWpfApp1\bin\Debug\TelerikWpfApp1.exe" />
</configuration>
```	
In your test code initialization, you read these settings by simply setting the UseConfig flag to true when calling the Manager() constructor. If you use the BaseTest template (which is what the VsUnit, MbUnit, NUnit and xUnit templates do) this call is done for you by BaseTest during the Initialize call:

```C#
Manager mgr = new Manager(true);
```
```VB
Dim myManager As Manager = New Manager(True)
```

**Note:** If you are using Telerik's BaseTest (which the Telerik VS item templates use), there is no need to for your test code to read from the app.config file as shown above. The base class already does that for you. Read the item template's comments for the initialization routine for more details.



