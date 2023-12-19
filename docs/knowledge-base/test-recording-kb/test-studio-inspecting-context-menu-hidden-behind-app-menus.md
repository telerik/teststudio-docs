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

When working with Test Studio's highlighting quick menu in recording mode on a combobox or context menu in the tested application, you may encounter an issue where the Test Studio menu is hidden behind the app menus. This makes it difficult to interact with the elements using the Test Studio recorder.

## Solution

To work around this issue, follow these steps:

1. Start the recording session and record click actions on the combobox or context menu elements directly, instead of using the Test Studio quick menu.
2. This will add a step and an element to the test.
3. Use the recorded element to add steps offline through the Step Builder.
4. Once you have the desired steps, you can remove the recorded click step if it is not necessary.

Alternatively, you can use the DOM explorer in the Advanced Recording tool to work with the combobox or context menu elements. Here's how:

1. Open the Advanced Recording tool during a recording session.
2. Switch to the application and open the combobox or context menu.
3. Press the 'Scroll Lock' key to freeze the DOM in its current state.
4. Switch back to the Advanced Recording window and search for the desired elements in the DOM.
5. Select the desired element and add steps from the Element steps tab.


