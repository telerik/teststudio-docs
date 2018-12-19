---
title: Rendering Differences
page_title: My Verification Works in IE but not in Firefox
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# My Verification Works in IE but not in Firefox


## PROBLEM

My recorded verification step works in IE but fails in Firefox.


## SOLUTION

Test Studio tries very hard to isolate you from browser differences, but cannot do so 100% in all cases. For example, IE will translate **&nbsp**; into a single space character before passing it to IE. But Firefox does not do this. As a result if you're trying to do a string comparison of some text, it will pass when you record it in IE, but fail when you try to execute the test in Firefox.

One quick solution is to include two separate verification steps and specify which browser each step will run against. All test steps include a **RunsAgainst** property setting:

![RunAgainst][1]

The default is **AllBrowsers**. Copy your verification step, set one to **InternetExplorerOnly**, and the other to **FirefoxOnly**. Adjust the verification for Firefox to work and your test will pass no matter which browser you target for execution.

If you need to do a similar action in code, you can use code like this:

```C#
if (ActiveBrowser.BrowserType == BrowserType.InternetExplorer)
{
    // Do IE specific action
}
else if (ActiveBrowser.BrowserType == BrowserType.FireFox)
{
    // Do Firefox specific action
}
else
{
    throw new ApplicationException("Unknown browser type");
}
```
```VB
' Do IE specific action
If ActiveBrowser.BrowserType = BrowserType.InternetExplorer Then
' Do Firefox specific action
ElseIf ActiveBrowser.BrowserType = BrowserType.FireFox Then
Else
    Throw New ApplicationException("Unknown browser type")
End If
```


[1]: /img/troubleshooting-guide/verification-problems-tg/work-ie-not-ff/fig1.png