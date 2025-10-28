---
title: Using the HTTP Proxy
page_title: Using the HTTP Proxy
description: "Learn how to enable and use the HTTP proxy in Test Studio coded tests. Includes setup instructions and code examples for intercepting HTTP requests and responses."
position: 1
---
# Using the HTTP Proxy in Test Studio

The Telerik Testing *Framework ArtOfTest.WebAii.Messaging.Http* namespace contains classes to intercept HTTP requests and responses. However, using these classes in a Test Studio coded step and executing against browsers other than Internet Explorer, the HTTP proxy may not become enabled. To use this code in a Test Studio test, <a href="/features/project-settings/General" target="_blank">enable the HTTP proxy</a> in the Test Studio Project Settings.

![http proxy][1]

The project setting 'Use http proxy' enables the HTTP proxy for the use of the HTTP proxy classes in Test Studio coded steps. It functions like the following line from the HTTP Proxy code sample, which is only necessary in Telerik Testing Framework tests:


```C#
// Override the settings you want. For example:
settings.Web.UseHttpProxy = true;
```


[1]: /img/advanced-topics/coded-samples/general/using-the-http-proxy/fig1.png
