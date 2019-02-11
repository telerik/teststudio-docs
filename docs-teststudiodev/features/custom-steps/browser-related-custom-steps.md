---
title: Custom Steps Related to Browser State
page_title: Custom Steps Related to Browser State | Test Studio Dev Documentation
description: Custom steps which can change or affect the browser status. 
slug: features/custom-steps/browser-related-custom-steps
position: 4
---
# Custom Steps Related to Browser State

The <a href="/features/recorder/step-builder" target="_blank">Step Builder</a> allows you to add steps which will manipulate the browser. These steps can be found in the _Common_ section of Step Builder.

![Common Section](images/step-builder-common.png)

## Maximize Browser

Inserting a _Maximize Browser_ step will change the browser window state - maximize, minimize or restore - depending on the selected from the dropdown option.

![Maximize Browser Step](images/maximize-browser.png)

## Clear Browser Cache

Inserting a _Clear Cache_ step will clear __all__ cookies, temp files and/or history from the active browser - depending on the requirements some or all of these could be selected.

![Clear Cache Step](images/clear-browser-cache.png)

This could be useful if you want to start a test against a clean browser without saved information (like username and password), or saved state information (if a user is logged in, last visit date, preferences, etc.).

> __Safari__ doesn't support clearing cache.

## Refresh Browser

Inserting a _Refresh Browser_ step will refresh the active browser.

![Browser Refresh Step](images/refresh-browser.png)

## Inspection Point

Inserting an _Inspection Point_ step will pause the test and display the DOM Explorer at this point. This is useful while debugging a test to view and inspect the DOM tree at a specific point of the execution - to explore if a specific element remains as you originally recorded it or its <a href="/features/elements-explorer/find-element" target="_blank">Find Expression</a> requires modification.

![Inspect Browser DOM Step](images/inspect-dom-step.png)

The test will remain paused until you close the DOM Explorer window.

![DOM Window at Paused Test](images/inspect-dom-test-paused.png)