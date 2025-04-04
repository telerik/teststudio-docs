---
title: Translators Project Settings
page_title: Translators Project Settings
description: "Test Studio comes with built-in translators for the Telerik components. Test Studio provides Basic translators for HTML, Silverlight, and WPF, and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular, Telerik UI for Blazor"
position: 8
---
# Translators Project Settings

The <a href="/getting-started/test-recording/translators" target="_blank">built-in translators</a> are __extensions that open up an element to work with Test Studio__ and thus allow interaction with the Elements Menu exposing a rich set of verification tasks.

> Check <a href="/features/project-settings/overview" target="_blank">here how to open the **Project Settings** window</a>. 

This section of the <a href="/features/project-settings/overview" target="_blank">Project Settings</a> allows you to __adjust the version of the Telerik and Kendo UI components__ used to build the application under test and lets Test Studio apply the matching translators. From this menu you can review and __disable/enable the components__ for which a translator is available.

![Translators Project Settings][1]

## Select the Version of the Telerik Components under Test

The __Telerik Components Under Test__ section lets you instruct the translators' version to match the version of the UI components in the tested page for this project. This setting applies to both the <a href="/automated-tests/recording/recording-telerik-kendo-ui-components" target="_blank">recording</a> and quick execution flows and allows you to smoothly create tests and run these for various applications. The same setting is exposed in the <a href="/features/test-lists/test-list-settings" target="_blank">test list settings</a> and can be set individually per test list.

![Telerik Components Under Test Version][2]

### How to Know Which is the Version of Components Used in the Tested Page?

As Quality Assurance Engineer you often don't know what type and version of UI components was used to create the application you need to automate. And since there is no convenient way to identify the version of the components in an already built and deployed application, the __most reliable approach is to contact the development team__ and discuss the topic internally.

### Test Studio Mapping to UI Components Versions

In the below grid you can find the versions of the supported UI components matching the translators versions from the list.

## Telerik UI for Blazor

| Release    | Version  |
|------------|----------|
| R32021     | 2.27.0   |
| R12022     | 3.0.0    |
| R12022SP1  | 3.1.0    |
| R22022     | 3.3.0    |
| R22022SP1  | 3.4.0    |
| R32022     | 3.6.0    |
| R12023     | 4.0.0    |
| R12023SP1  | 4.1.0    |
| R22023     | 4.3.0    |
| R32023     | 4.6.0    |
| R22024     | 6.0.0    |

## Telerik UI for ASP.NET AJAX

| Release    | Version      |
|------------|--------------|
| R32021     | 2021.3.914   |
| R12022     | 2022.1.119   |
| R12022SP1  | 2022.1.302   |
| R22022     | 2022.2.511   |
| R22022SP1  | 2022.2.622   |
| R32022     | 2022.3.913   |
| R12023     | 2023.1.117   |
| R12023SP1  | 2023.1.314   |
| R22023     | 2023.2.606   |
| R32023     | 2023.3.1010  |
| R22024     | 2024.2.513   |

## Kendo UI for jQuery

| Release    | Version      |
|------------|--------------|
| R32021     | 2021.3.914   |
| R12022     | 2022.1.119   |
| R12022SP1  | 2022.1.301   |
| R22022     | 2022.2.510   |
| R22022SP1  | 2022.2.621   |
| R32022     | 2022.3.913   |
| R12023     | 2023.1.117   |
| R12023SP1  | 2023.1.314   |
| R22023     | 2023.2.606   |
| R32023     | 2023.3.1010  |
| R22024     | 2024.2.514   |

## Kendo UI for Angular

| Release R32021           |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 5.4.0             |
| KendoAngularButton       | kendo-angular-buttons      | 6.3.0             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 5.4.0             |
| KendoAngularDialog       | kendo-angular-dialog       | 5.1.1             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 5.4.0             |
| KendoAngularGrid         | kendo-angular-grid         | 5.4.0             |
| KendoAngularInputs       | kendo-angular-inputs       | 7.4.0             |
| KendoAngularPager        | kendo-angular-pager        | 1.0.0             |
| KendoAngularPanelBar     | kendo-angular-layout       | 6.3.0             |
| KendoAngularSwitch       | kendo-angular-inputs       | 7.4.0             |
| KendoAngularTabStrip     | kendo-angular-layout       | 6.3.0             |
| KendoAngularWindow       | kendo-angular-dialog       | 5.1.1             |

| Release R12022           |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 6.0.0             |
| KendoAngularButton       | kendo-angular-buttons      | 7.0.0             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 6.0.0             |
| KendoAngularDialog       | kendo-angular-dialog       | 6.0.0             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 6.0.0             |
| KendoAngularGrid         | kendo-angular-grid         | 6.0.0             |
| KendoAngularInputs       | kendo-angular-inputs       | 8.0.0             |
| KendoAngularPager        | kendo-angular-pager        | 3.0.0             |
| KendoAngularPanelBar     | kendo-angular-layout       | 6.4.0             |
| KendoAngularSwitch       | kendo-angular-inputs       | 8.0.0             |
| KendoAngularTabStrip     | kendo-angular-layout       | 6.4.0             |
| KendoAngularWindow       | kendo-angular-dialog       | 6.0.0             |

| Release R12022SP1        |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 6.0.1             |
| KendoAngularButton       | kendo-angular-buttons      | 7.0.3             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 6.0.1             |
| KendoAngularDialog       | kendo-angular-dialog       | 6.0.2             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 6.0.1             |
| KendoAngularGrid         | kendo-angular-grid         | 6.1.0             |
| KendoAngularInputs       | kendo-angular-inputs       | 8.0.7             |
| KendoAngularPager        | kendo-angular-pager        | 3.0.2             |
| KendoAngularPanelBar     | kendo-angular-layout       | 6.5.1             |
| KendoAngularSwitch       | kendo-angular-inputs       | 8.0.7             |
| KendoAngularTabStrip     | kendo-angular-layout       | 6.5.1             |
| KendoAngularWindow       | kendo-angular-dialog       | 6.0.2             |

| Release R22022           |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 7.0.1             |
| KendoAngularButton       | kendo-angular-buttons      | 8.0.0             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 7.0.1             |
| KendoAngularDialog       | kendo-angular-dialog       | 7.0.0             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 7.0.1             |
| KendoAngularGrid         | kendo-angular-grid         | 7.0.1             |
| KendoAngularInputs       | kendo-angular-inputs       | 9.0.1             |
| KendoAngularPager        | kendo-angular-pager        | 4.0.0             |
| KendoAngularPanelBar     | kendo-angular-layout       | 7.0.1             |
| KendoAngularSwitch       | kendo-angular-inputs       | 9.0.1             |
| KendoAngularTabStrip     | kendo-angular-layout       | 7.0.1             |
| KendoAngularWindow       | kendo-angular-dialog       | 7.0.0             |

| Release R22022SP1        |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 7.0.2             |
| KendoAngularButton       | kendo-angular-buttons      | 8.0.0             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 7.0.2             |
| KendoAngularDialog       | kendo-angular-dialog       | 7.1.2             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 7.0.2             |
| KendoAngularGrid         | kendo-angular-grid         | 7.2.0             |
| KendoAngularInputs       | kendo-angular-inputs       | 9.0.3             |
| KendoAngularPager        | kendo-angular-pager        | 4.0.0             |
| KendoAngularPanelBar     | kendo-angular-layout       | 7.1.0             |
| KendoAngularSwitch       | kendo-angular-inputs       | 9.0.3             |
| KendoAngularTabStrip     | kendo-angular-layout       | 7.1.0             |
| KendoAngularWindow       | kendo-angular-dialog       | 7.1.2             |

| Release R32022           |                            |                   |
|--------------------------|----------------------------|-------------------|
| **Translator Name**      | **Component Name**         | **Component Version** |
| KendoAngularAutoComplete | kendo-angular-dropdowns    | 7.2.0             |
| KendoAngularButton       | kendo-angular-buttons      | 8.1.0             |
| KendoAngularComboBox     | kendo-angular-dropdowns    | 7.2.0             |
| KendoAngularDialog       | kendo-angular-dialog       | 7.1.3             |
| KendoAngularDropdownList | kendo-angular-dropdowns    | 7.2.0             |
| KendoAngularGrid         | kendo-angular-grid         | 7.3.1             |
| KendoAngularInputs       | kendo-angular-inputs       | 10.0.0            |
| KendoAngularPager        | kendo-angular-pager        | 4.0.5             |
| KendoAngularPanelBar     | kendo-angular-layout       | 7.1.3             |
| KendoAngularSwitch       | kendo-angular-inputs       | 10.0.0            |
| KendoAngularTabStrip     | kendo-angular-layout       | 7.1.3             |
| KendoAngularWindow       | kendo-angular-dialog       | 7.1.3             |

| Release    | Version  |
|------------|----------|
| R12023     | 11.0.0   |
| R12023SP1  | 11.4.0   |
| R22023     | 13.0.0   |
| R32023     | 14.0.0   |
| R22024     | 16.0.0   |

## Available Translators

The __Available Translators__ section lists __all built-in translators__ that are currently available in Test Studio. All translators are enabled by default, which is the __recommended setup__. Each of the built-in translators can be disabled and not used while recording and executing tests, but we strongly recommend contacting the Test Studio Support Team before  applying changes to the enabled translators.

![Available Translators][3]

[1]: /img/features/project-settings/translators/fig1.png
[2]: /img/features/project-settings/translators/fig2.png
[3]: /img/features/project-settings/translators/fig3.png
