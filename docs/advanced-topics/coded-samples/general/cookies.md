---
title: Cookies
page_title: Get/Set Cookies in Code
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Get/Set Cookies in Code#

Here is a working code sample. Notice the URL must be different for SetCookie versus GetCookies:

```C#
Manager.LaunchNewBrowser();
 
const string url = "www.google.com";
{
    var cookie = new Cookie("foo", "bar", "/", url);
    cookie.Expires = DateTime.MaxValue;
    var ok = ActiveBrowser.Cookies.SetCookie(cookie);
}
 
var c = ActiveBrowser.Cookies.GetCookies("http://www.google.com");
var count = c.Count;
 
Log.WriteLine(count.ToString());
foreach (Cookie cookie in ActiveBrowser.Cookies.GetCookies("http://www.google.com"))
{
    Log.WriteLine(cookie.Name);
}
```

```VB
Manager.LaunchNewBrowser()
 
Const  url As String = "www.google.com"
If True Then
    Dim cookie = New Cookie("foo", "bar", "/", url)
    cookie.Expires = DateTime.MaxValue
    Dim ok = ActiveBrowser.Cookies.SetCookie(cookie)
End If
 
Dim c = ActiveBrowser.Cookies.GetCookies("http://www.google.com")
Dim count = c.Count
 
Log.WriteLine(count.ToString())
For Each cookie As Cookie In ActiveBrowser.Cookies.GetCookies("http://www.google.com")
    Log.WriteLine(cookie.Name)
Next
```

