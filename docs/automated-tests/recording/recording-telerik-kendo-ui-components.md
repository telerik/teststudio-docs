---
title: How to Record Steps for Telerik and Kendo UI Components 
page_title: How to Record Steps for Telerik and Kendo UI Components
description: "Test Studio records specific steps to handle Telerik and Kendo UI Components. Find out how to record test scenarios in applications built with the Telerik and Kendo controls. Find out how to automate specific actions for Telerik and Kendo UI Components "
position: 3
---
# How to Automate Application Built with Telerik and Kendo UI Components

Test Studio recorder toolbar recognizes the Telerik and Kendo UI controls and exposes specific actions and verifications through the <a href="/features/recorder/translators" target="_blank">built-in translators</a> while you record the test scenario.

Read further how to record test scenarios with the built-in translators.

## Record a Test Scenario in Application Built with Telerik and Kendo UI

For this demonstration we use the Kendo Angular Grid component official <a href="https://www.telerik.com/kendo-angular-ui/components/grid/" target="_blank">demo page</a> on the Telerik site. <a href="/automated-tests/recording/overview" target="_blank">Start a recording session</a> choosing the URL for the application to automate. Once the browser loads the page and recorder is attached <a href="/automated-tests/recording/hover-over-highlighting#enable-or-disable-highlighting-of-elements" target="_blank">enable the element highlight</a> and hover the mouse over elements - the recording toolbar fans out to __indicate more specific translators progressively__. It shows enhanced highlighting in the form of colored borders around a "translated" element, indicating how elements are contained within one another. The below example indicates translators for a KendoUI Angular Grid cell and the represented menu items are:

* GridDataCell
* GridDataItem
* HtmlTable
* Grid

![Hover mouse over Kendo Grid][0]

As you move the mouse over the items in the menu, the respective element on page gets highlighted. Select the <a href="/features/verifications/quick-verification" target="_blank">Quick Steps</a> option on the Elements Menu to see a list of verification tasks for the specific element and choose the suitable as per the scenario. Hit any of the pages from the list to switch to and Test Studio records a custom step for paging through the grid. Without the translator you could not get into that level of detail so easily.

![Sample test steps for Kendo Angular grid][1]

> __Tip__
><br>
><br>
> Don't miss to read the blog post about <a href="https://www.telerik.com/blogs/automated-testing-of-kendo-ui-made-easy" target="_blank">__Automated Testing for Kendo UI Made Easy__</a>.

The recording experience for other Telerik and Kendo UI components is the same for the different controls. It is only the colour of the highlighting borders which differs for the various type of components.

![Hover mouse over Blazor DropdownList][2]

The steps added in the test are custom for the specific control you automate.

![Test steps for Blazor DropdownList][3]

> __Tip__
><br>
><br>
> Speed up your scenario recording knowledge with this neat <a href="https://www.telerik.com/videos/teststudio/getting-started-with-using-the-test-studio-translators-for-telerik-ui-for-blazor" target="_blank">video tutorial</a> that __demonstrates how to benefit from the Blazor translators in Test Studio__.

## Translators Versioning

Test Studio is committed to support the latest released UI components as well as to keep backwards compatibility for applications built with any previous version of Kendo and Telerik UI. During 2022 the Telerik and Kendo UI components introduced fundamental changes in the components composition and overall look. This is why __Test Studio R1 2022 SP1 (v.2022.1.412) ships with versioning mechanism__ and allows you to choose the translators/components version to use in a project.

### The Important Topics to Note about the Translators Versioning

* The _Translators Version_ setting is __set on project level__ through the <a href="/features/project-settings/translators" target="_blank">Project Settings -> Translators</a>. This setting is __used for recording and quick test execution__.
* Mapping of the matching versions of the releases and components is listed <a href="/features/project-settings/translators#test-studio-mapping-to-ui-components-versions" target="_blank">here</a>. 
* __Test lists created in the project inherits the current value of the  _Translators Version_ setting on project level__. From that point on the setting is __maintained separately__ per each test list in the dedicated test list settings.
* All existing test lists scheduled for remote runs automatically upload the changes in their settings to the Storage. Thus no downtime of test list runs is expected.
* When you open any existing project in Test Studio v.2022.1.412, it gets upgraded - this process __adds the _Translators Version_ setting for the project and for the existing test lists__ following the below version mapping logic:

    * A project __created and last used in Test Studio v.2021.1.215 or any previous version__ gets upgraded in v.2022.1.412 and the _Translators Version_ setting for the project and for all test lists is set to R32021.
    * A new __project created in Test Studio v.2022.1.412 uses the _Translators Version_ setting with value _'Latest'___. That way it indicates the translators support the latest available version of the Telerik and Kendo components. If you leave the setting that way, it will be converted to the specific version (R12022SP1) when the project is upgraded in a new version of Test Studio.



[0]: /img/automated-tests/recording/recording-translators/highlight-components.gif
[1]: /img/automated-tests/recording/recording-translators/fig1.png
[2]: /img/automated-tests/recording/recording-translators/fig2.png
[3]: /img/automated-tests/recording/recording-translators/fig3.png
