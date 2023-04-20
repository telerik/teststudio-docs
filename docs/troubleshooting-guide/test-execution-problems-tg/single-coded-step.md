---
title: Run a selected single coded step fails
page_title: Run a selected single coded step fails
description: "Executing a single coded step in an active recording session fails to find the used elements in the code. Can I run only the coded step while debugging the Test Studio test? "
position: 1
---
# Why running a selected single coded step fails?


## Problem

When a single coded step is selected and run it fails with the following exception:

*System.ArgumentNullException: Start reference element can't be null. Please make sure the DOM is loaded by either calling NavigateTo() to a page or add browser RefreshDomTree() prior to the code which needs the DOM.*

This happens because a single coded step does not call ActiveBrowser.RefreshDomTree() call as it needs the DOM to execute against. We handle that internally for Navigate or non-coded steps with elements because we can figure out we need the DOM.

## Solution

You should solve this issue by adding ActiveBrowser.RefreshDomTree() as the first row in the coded step.