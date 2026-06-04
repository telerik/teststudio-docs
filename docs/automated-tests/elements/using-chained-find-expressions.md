---
title: Chained Find Expressions
page_title: Using Chained Find Expressions
description: Using Chained Find Expressions. Building find expressions for Hierarchical controls such as tree views, grid views, etc. In these and other situations, the user is less concerned with the sequence of the items in the control, and more with their position relative to one another. Test Studio will usually record find logic based on the element’s sequential position within the control. A chained find expression will locate the first or parent element, and limit the search for the target element in the DOM under that parent element.
previous_url: /user-guide/knowledge-base/project-configuration/usingchainedfindexpressions.aspx
position: 2
---
# Using Chained Find Expressions

In most cases, Test Studio’s default find logic can dependably find target elements. By prioritizing unique element IDs, parent elements and element content, Test Studio produces durable find expressions for a wide variety of elements. But some controls are inherently difficult to find with Test Studio’s default logic.

One type of controls that pose a challenge for Test Studio’s default find logic are hierarchical controls such as tree views.

![TreeView](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig1.png)

In these and other situations, the user is less concerned with the sequence of the items in the control, and more with their position relative to one another.

However, Test Studio will usually record find logic based on the element’s sequential position within the control.

![FindExpression](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig2.png)

This is a job where chained find expression will suit perfectly. A chained find expression will locate the first or parent element, and limit the search for the target element in the DOM under that parent element.

## Version 2019 R1 and Later

### Select the Target Element

Select the target element in the **Elements Explorer** and select *Edit Element* from the context menu.

![Edit Element](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig103.png)

This will open the *Edit Element* pane, where you can modify the default recorded find logic and change <a href="/features/elements-explorer/find-element#version-2019-r1-and-later" target="_blank">how to locate the element</a>.

![Find settings](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig104.png)

For many tree nodes and other hierarchical controls, Test Studio will initially record a chained find expression.
This can be easily identified by the way the two filters for the parent and child elements are separated and selecting any of these change the element in the DOM tree.

![Chained Find Expression](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig105.gif)

### Change the Find Logic

Edit the find expression to reflect the desired find strategy. The goal is to accurately identify the parent element in the whole page DOM tree, then give a find logic that is accurate for the target element, given it is beneath the parent element in the DOM.

You can manually edit the filter options and remove the old sequential one.

![Manually Add Filter](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig106.gif)

Or replace using one of the rules with a suggested filter and remove the old sequential one.

![Choose from the Suggested Filters](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig107.gif)

You can use the ***Validate Expression*** button to confirm the selected filters are pointing to the desired element.

![Validate Find Expression](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig108.png)

## Version 2018 R3 and Earlier

1. First, select the target element in the **Elements Explorer** and select Edit in Live from the context menu.

![Edit in Live](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig3.png)

This will open the Find Element menu. You can choose <a href="/features/elements-explorer/find-element" target="_blank">how to locate the element</a>. Once you have located the element, you can change the find settings.

![Find settings](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig4.png)

For many tree nodes and other hierarchical controls, Test Studio will initially record a chained find expression. You can identify this by the way the filter(s) for the parent element (1) is connected to the filter(s) for the target element (2) by a blue diagonal arrow. If not, you can chain a new set of filters to an existing set by clicking the blue arrow.

2. Change the find logic to reflect the desired find strategy. The goal is to accurately identify the parent element, then give a find logic that is accurate for the target element, given it is beneath the parent element in the DOM.
3. You can manually edit the filter options, or replace one of the rules with a suggested filter from the left side.

![Change find settings](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig5.png)

Selecting a suggestion from the left will add it to the existing filter(s) for the selected element in the chained find.

![Add new filter](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig6.png)

Once you have added  a new filter, you can remove the old sequential one.

![Delete filter](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig7.png)

The result is a working chained find expression. Test Studio will look for the parent element (1) first, then find the target element (2).

![New expression](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig8.png)

You can confirm that your chained find works by using the **Validate** button.

![Validate](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig9.png)

Once you validate and save the new find logic, you can select the element in the Elements Explorer and locate it in the DOM.

![Locate in DOM](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig10.png)

This can help you see how the chained find expression will work against the DOM. The target element highlighted should be beneath the parent element in the DOM hierarchy.

![Locate in DOM](/img/knowledge-base/project-configuration-kb/using-chained-find-expressions/fig11.png)

## See Also

* <a href="http://www.telerik.com/videos/teststudio/test-studio---flexible-locators-" target="_blank">Watch a video tutorial on chained find expressions</a>

