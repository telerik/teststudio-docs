---
title: Recorder Blocks WPF Popup
page_title: Recorder Blocks WPF Pop-up
description: "Resolve Recorder Blocks WPF Pop-up"
position: 1
---
# Recorder Blocks WPF Pop-up

## PROBLEM

When recording against a WPF application, an expected pop-up modal dialog never appears.

## SOLUTION

This can result from an overlay surface in the WPF application. The solution is to ensure that an Adorner is not attached to a null window object. This is necessary because the Test Studio recorder is now <a href="http://msdn.microsoft.com/en-us/library/system.windows.application.windows.aspx" target="_blank">included in the window collection</a>.
