---
title: Read WPF AutomationProperties in Test Studio 
description: Learn how to read WPF AutomationProperties in Test Studio.
type: how-to
page_title: Read WPF AutomationProperties in Test Studio
slug: read-wpf-automation-properties
tags: automation, WPF, Test Studio
res_type: kb
---
## Environment

| Property | Value |
|---|---|
| Product | Progress Telerik Test Studio |
| Version | 2023.3.1011.1 |

## Description
How to read WPF AutomationProperties in Test Studio.

## Solution
Automation properties are defined as a set of  an attached properties of a WPF element, so you can read them using GetAttachedProperty method. 
Here's an example of how to read the `ItemStatus` property:

```csharp
var itemStatus = <Your-Wpf-Element>.GetAttachedProperty<string>("System.Windows.Automation.AutomationProperties", "ItemStatus");
```

Please note that the code above will work only when automation property values are set in the XAML of your WPF application.


## Notes
None.

## See Also
None.