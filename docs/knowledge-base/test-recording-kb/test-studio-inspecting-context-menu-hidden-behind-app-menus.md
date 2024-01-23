---
title:  Test Studio's Recording Quick Menu Stays Behind App Menus
description: This article provides a workaround for the issue where Test Studio's highlighting quick menu is hidden behind the menus of the tested application.
type: how-to
page_title: Test Studio Highlighting Quick Menu Hidden Behind App Menus
slug: test-studio-inspecting-context-menu-hidden-behind-app-menus
tags: test-studio, inspecting-context-menu, hidden-menu, workaround
res_type: kb
---


## Description

When working with Test Studio's <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">highlighting quick menu in recording mode</a> on a combobox or context menu in the tested application, you may encounter an issue where the Test Studio menu is hidden behind the app menus. This makes it difficult to interact with the elements using the Test Studio recorder.

## Solution 1

To workaround the issue, follow these steps:

1. Start the recording session and <a href="/automated-tests/recording/overview#how-to-add-steps-in-the-test" target="_blank">record click actions</a> on the combobox or context menu elements directly, instead of using the Test Studio quick menu.
2. This will add a step and an element to the test.
3. Use the <a href="/features/custom-steps/overview#add-step-for-a-recorded-element" target="_blank">recorded element to add steps offline through the Step Builder</a>.
4. Once you have the desired steps, you can remove the recorded click step if it is not necessary.

## Solution 2

Alternatively, you can use the DOM explorer in the Advanced Recording tool to work with the combobox or context menu elements. Here's how:

1. Open the Advanced Recording Tools window from the <a href="/automated-tests/recording/overview#what-is-the-compact-recorder" target="_blank">compact recorder</a>.
2. Switch to the application and open the combobox or context menu.
3. Press the 'Scroll Lock' key to freeze the DOM in its current state. The <a href="/features/recorder/advanced-recording-tools/dom-explorer#toolbar-options" target="_blank">option to freeze the DOM</a> stops the auto-refresh and keeps the DOM as it was at the time of the freeze. 
4. Switch back to the Advanced Recording window and search for the desired elements in the DOM.
5. Select the element and <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">add steps from the Element steps tab</a>.


