---
title: Configure Browser In Code
page_title: Configure Browser In Code
description: "Test Studio Testing Framework supports browser calibration in coded tests. Configure execution browser in code. "
position: 1
---
#Configure Browser In Code

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