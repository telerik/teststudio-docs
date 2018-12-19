---
title: Run a selected single coded step fails
page_title: Run a selected single coded step fails
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Why running a selected single coded step fails?


##Problem

When a single coded step is selected and run it fails with the following exception:

*System.ArgumentNullException: Start reference element can't be null. Please make sure the DOM is loaded by either calling NavigateTo() to a page or add browser RefreshDomTree() prior to the code which needs the DOM.*

This happens because a single coded step does not call ActiveBrowser.RefreshDomTree() call as it needs the DOM to execute against. We handle that internally for Navigate or non-coded steps with elements because we can figure out we need the DOM.

##Solution

You should solve this issue by adding ActiveBrowser.RefreshDomTree() as the first row in the coded step.