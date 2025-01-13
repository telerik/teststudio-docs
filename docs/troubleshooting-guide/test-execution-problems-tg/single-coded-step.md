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

## Cause

This happens because a single coded step is not set to automatically call refresh of the DOM but at the same time it needs any DOM tree to execute against. 

## Solution

Add a statement to refresh the DOM tree as first row in the coded step.

```C# 
// Use Manager.ActiveBrowser for a web application 
Manager.ActiveBrowser.RefreshDomTree();

// Use Manager.ActiveApplication for a wpf application 
Manager.ActiveApplication.MainWindow.RefreshVisualTrees();
```
