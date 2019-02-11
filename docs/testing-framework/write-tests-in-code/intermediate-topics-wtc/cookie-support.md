---
title: Cookie Support
page_title: Cookie Support
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Cookie Support#

Using the CookieManager class you can:

* Retrieve cookies for a particular website from the browser

* Set the contents of a cookie in the browser

* Create a new cookie in the browser

* Delete a cookie in the browser

##Retrieving Cookies##

There are two functions that can be used to retrieve cookies from the browser:


```C#
public CookieCollection GetCookies (string url)
public CookieCollection GetCookies (Uri uri)
```
```VB
Public Function GetCookies(ByVal url As String) As System.Net.CookieCollection
Public Function GetCookies(ByVal uri As System.Uri) As System.Net.CookieCollection
```

These functions retrieve all the cookies from the browser for the specified website. For example:

```C#
// Query the cookie
System.Net.CookieCollection siteCookies = ActiveBrowser.Cookies.GetCookies("http://www.telerik.com");
```
```VB
' Query the cookie
Dim siteCookies As System.Net.CookieCollection = ActiveBrowser.Cookies.GetCookies("http://www.telerik.com")
```

##Creating and Setting Cookies##

Below is an example of how to create or set a cookie. If the cookie already exists, it will be overwritten. If it does not exist, a new cookie will be created in the browser:

```C#
// Let's create a new cookie for a url.
ActiveBrowser.Cookies.SetCookie(new System.Net.Cookie("WebAii", "Rocks", "/", "http://www.telerik.com"));
```
```VB
' Let's create a new cookie for a url.
ActiveBrowser.Cookies.SetCookie(New System.Net.Cookie("WebAii", "Rocks", "/", "http://www.telerik.com"))
```

##Deleting Cookies##

Here is an example of how to delete a cookie:

```C#
// Now delete the cookie.
ActiveBrowser.Cookies.DeleteCookie(siteCookies[0]);
```
```VB
' Now delete the cookie.
ActiveBrowser.Cookies.DeleteCookie(siteCookies(0))
```

A simple foreach loop can be used to delete all the cookies for a particular website:

```C#
// Purge any cookies associated with this server
System.Net.CookieCollection cookies = ActiveBrowser.Cookies.GetCookies(Settings.Current.BaseUrl);
foreach (System.Net.Cookie cookie in cookies)
{
    ActiveBrowser.Cookies.DeleteCookie(cookie);
}
```
```VB
' Purge any cookies associated with this server
Dim cookies As System.Net.CookieCollection = ActiveBrowser.Cookies.GetCookies(Settings.Current.BaseUrl)
For Each cookie As System.Net.Cookie In cookies
     ActiveBrowser.Cookies.DeleteCookie(cookie)
Next cookie
```