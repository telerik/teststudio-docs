---
title: Set Step to Run for Specific Browser
page_title: A Recorded Step Behaves Differently in the Different Browsers
description: "Test Studio tests tend to be isolated from the browser differences and each type of step works for all supported browsers. Still is available the option to set specific step to run for one browser only. "
position: 1
---

# A Recorded Step Behaves Differently in the Different Browsers

## PROBLEM

* My recorded step behaves differently in the different browsers.
* There is a specific action, which needs to be performed only in one type browser.

__How can I set a step to run against specific browser only?__

## SOLUTION

Test Studio strives to isolate you from browser differences, but in the cases when specific action or verification needs to be performed only for specific browsers, you can do so.

One quick solution is to include two separate steps and specify which browser each step will run against. All test steps include a **RunsAgainst** property setting:

![RunAgainst][1]

The default is **AllBrowsers**. Copy your step and set one to **InternetExplorerOnly**, for example, and the other to **FirefoxOnly**. That way the specific step will execute only against the specified browser.

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