---
title: Test Results (VS Plugin)
page_title: Test Results (VS plugin)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/test-results/test-results-vs-plugin.aspx, /user-guide/test-results/test-results-vs-plugin, /getting-started/test-results/test-results-vs
position: 1
---
# Test Results (VS plugin) #

## Visual Studio 2012 and later ##

Once you execute your test using the <a href="/getting-started/test-execution/vs-2012-test-explorer" target="_blank">Visual Studio Test Explorer</a> you can see the results right under Test Explorer.

![View test results 2012][6]

A /**TestResults** folder is created in your project directory. It contains a *trx* test results file and a sub-folder with a matching name. The syntax is *UserName_MachineName Year-Month-Day Time*.

![Test results folder][3]

The *trx* result is simply an XML file that contains the conditions that the test was run under and the results of the test. Change the extension to xml to see the raw XML in the browser.

![trx file][4]

That matching sub-folder contains an \ **Out** directory with the output from the text and screen images if your test included browser/desktop capture steps.

![Out folder][5]

[3]: /img/general-information/test-results/test-results-vs/fig3.png
[4]: /img/general-information/test-results/test-results-vs/fig4.png
[5]: /img/general-information/test-results/test-results-vs/fig5.png
[6]: /img/general-information/test-results/test-results-vs/fig6.png
