---
title: How to Record Steps for Telerik and Kendo UI Components 
page_title: How to Record Steps for Telerik and Kendo UI Components
description: "Test Studio records specific steps to handle Telerik and Kendo UI Components. Find out how to record test scenarios in applications built with the Telerik and Kendo controls. Find out how to automate specific actions for Telerik and Kendo UI Components "
position: 3
---
# How to Automate Application Built with Telerik and Kendo UI Components

Test Studio recorder toolbar recognizes the Telerik and Kendo UI controls and exposes specific actions and verifications for these while you record the test scenario.

Read further how to record test scenarios with the built-in translators.

## Record a Test Scenario in Application Built with Telerik and Kendo UI

For this demonstration we use the Kendo Angular Grid component official <a href="https://www.telerik.com/kendo-angular-ui/components/grid/" target="_blank">demo page</a> on the Telerik site. <a href="/automated-tests/recording/overview" target="_blank">Start a recording session</a> choosing the URL for the application to automate. Once the browser loads the page and recorder is attached <a href="/automated-tests/recording/hover-over-highlighting#enable-or-disable-highlighting-of-elements" target="_blank">enable the element highlight</a> and hover the mouse over elements - the recording toolbar fans out to __indicate more specific translators progressively__. It shows enhanced highlighting in the form of colored borders around a "translated" element, indicating how elements are contained within one another. The below example indicates translators for a KendoUI Angular Grid cell and the represented menu items are:

* GridDataCell
* GridDataItem
* HtmlTable
* Grid

![Hover mouse over Kendo Grid][0]

As you move the mouse over the items in the menu, the respective element on page gets highlighted. Select the <a href="/features/verifications/quick-verification" target="_blank">Quick Steps</a> option on the Elements Menu to see a list of verification tasks for the specific element and choose the suitable as per the scenario. Hit any of the pages from the list to switch to and Test Studio records a custom step for paging through the grid. Without the translator you could not get into that level of detail so easily.

![Sample test steps][1]

> __Tip__
><br>
><br>
> Don't miss to read the blog post about <a href="https://www.telerik.com/blogs/automated-testing-of-kendo-ui-made-easy" target="_blank">Automated Testing for Kendo UI Made Easy</a>.

The recording experience for other Telerik and Kendo UI components is the same for the different controls. It is only the colour of the highlighting borders which differs for the various type of components.

![Hover mouse over Blazor DropdownList][2]

> __Tip__
><br>
><br>
> Speed up your scenario recording knowledge with this neat <a href="https://www.telerik.com/videos/teststudio/getting-started-with-using-the-test-studio-translators-for-telerik-ui-for-blazor" target="_blank">video tutorial</a> that demonstrates how to benefit from the Blazor translators in Test Studio.

[0]: /img/automated-tests/recording/recording-translators/highlight-components.gif
[1]: /img/automated-tests/recording/recording-translators/fig1.png
[2]: /img/automated-tests/recording/recording-translators/fig2.png
