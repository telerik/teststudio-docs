---
title: Web Applications
page_title: Web Applications
description: Getting Started article describing how to record and playback a mobile Test Studio test.
slug: ms-getting-started-web
tags: ios, testing, started
previous_url: /test-studio-mobile/overview-mb/web-applications
publish: true
position: 1
---

> Although the Mobile testing module is in а process of discontinuation, Test Studio main product continues supporting <a href="https://www.telerik.com/teststudio/automated-website-responsive-testing" target="_blank">responsive testing of web applications</a> to help meeting the demand of mobile users.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

# Getting Started with Web Applications in Test Studio Mobile

This section walks you through the process of recording your first Test Studio Mobile web test and execute it in a browser (Mobile or Desktop). Before you start, please ensure the following:

* You have access to a Windows machine where Test Studio Ultimate will be installed. The Test Studio Mobile solution currently works only on Windows machines and installs as part of the Test Studio product.

## Connect Agent(Browser)

Connecting a web browser to Test Studio Mobile is a multi-step process that uses a built-in WebProxy. The proxy is responsible for injecting a Web Extension in every page that a web test navigates to.

* [Web Connection]({% slug ms-configure-tsm%})

##Record and Playback Test

Once the above setup is complete you can start

* [Recording your test]({% slug ms-record-test-web%})

or

* [Playback your test]({% slug ms-quick-execution%})


See Also
--------

+ [Elements Explorer]({% slug ms-elements-explorer%})
+ [Test Explorer]({% slug ms-test-explorer%})
+ [Project Explorer]({% slug ms-project-explorer%})