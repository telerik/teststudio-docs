---
title: Configure Browser In Code
page_title: Configure Browser In Code
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Configure Browser In Code#

Apart from manually configuring each of the browsers for test execution this could be also accomplished in code. 

```C#
//declare string variable to write possible errors in 
string error;
// to configure FireFox
Manager.ConfigureBrowser(BrowserType.FireFox, out error);
// to configure Chrome
Manager.ConfigureBrowser(BrowserType.Chrome, out error);
// to configure IE
Manager.ConfigureBrowser(BrowserType.InternetExplorer, out error);
// to configure Safari
Manager.ConfigureBrowser(BrowserType.Safari, out error);
// to configure Edge
Manager.ConfigureBrowser(BrowserType.MicrosoftEdge, out error);
```

```VB
Dim error As String
Manager.ConfigureBrowser(BrowserType.FireFox, error)
Manager.ConfigureBrowser(BrowserType.Chrome, error)
Manager.ConfigureBrowser(BrowserType.InternetExplorer, error)
Manager.ConfigureBrowser(BrowserType.Safari, error)
Manager.ConfigureBrowser(BrowserType.MicrosoftEdge, error)
```