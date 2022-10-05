---
title: Translators Project Settings
page_title: Translators Project Settings | Test Studio Dev Documentation
description: "Test Studio Dev comes with built-in translators for the Telerik components. Test Studio provides Basic translators for HTML, Silverlight, and WPF, and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular, Telerik UI for Blazor"
position: 7
---
# Translators Tab in Project Settings

The <a href="/features/recorder/translators" target="_blank">built-in translators</a> are __extensions that open up an element to work with Test Studio__ and allow interaction exposing a rich set of verification options.

In this section of the Project Settings you can set the __version of the Telerik and Kendo UI components__ used to build the application under test so that Test Studio applies the matching translators. From this menu you can review and __disable/enable the components__ for which a translator is available.

![Translators][1]

## Select the Version of the Telerik Components under Test

The __Telerik Components Under Test__ section lets you instruct the translators' version to match the version of the UI components in the tested page for this project. This setting applies to both the <a href="/features/recorder/translators" target="_blank">recording</a> and quick execution flows and allows you to smoothly create tests and run these for various applications. The same setting is exposed in the <a href="/features/test-execution/test-list-settings" target="_blank">test list settings</a> and can be set individually per test list.

![Translators version][2]

### How to Know Which is the Version of Components Used in the Tested Page?

As Quality Assurance Engineer you often don't know what type and version of UI components was used to create the application you need to automate. And since there is no convenient way to identify the version of the components in an already built and deployed application, the __most reliable approach is to contact the development team__ and discuss the topic internally.

### Test Studio Mapping to UI Components Versions

In the below grid you can find the versions of the supported UI components matching the translators versions from the list.

<p id="Blazor">
<table class="Tbl k-table">
    <colgroup>
        <col width="50%" />
        <col width="50%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="6" style="color:white;text-align:center;background-color:#70757d;font-weight:bold;text-align:left;">Telerik UI for Blazor<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R32021</td>
            <td colspan="6" style="text-align:center;">2.27.0</td>
        </tr>
        <tr>
            <td>R12022</td>
            <td colspan="6" style="text-align:center;">3.0.0</td>
        </tr>
        <tr>
            <td>R12022SP1</td>
            <td colspan="6" style="text-align:center;">3.1.0</td>
        </tr>
        <tr>
            <td>R22022</td>
            <td colspan="6" style="text-align:center;">3.3.0</td>
        </tr>
        <tr>
            <td>R22022SP1</td>
            <td colspan="6" style="text-align:center;">3.4.0</td>
        </tr>
        <tr>
            <td>R32022</td>
            <td colspan="6" style="text-align:center;">3.6.0</td>
        </tr>
    </tbody>
</table>
</p>

<p id="asp.net ajax">
<table class="Tbl k-table">
    <colgroup>
        <col width="50%" />
        <col width="50%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="6" style="color:white;text-align:center;background-color:#70757d;font-weight:bold;text-align:left;">Telerik UI for ASP.NET AJAX<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R32021</td>
            <td colspan="6" style="text-align:center;">2021.3.914</td>
        </tr>
        <tr>
            <td>R12022</td>
            <td colspan="6" style="text-align:center;">2022.1.119</td>
        </tr>
        <tr>
            <td>R12022SP1</td>
            <td colspan="6" style="text-align:center;">2022.1.302</td>
        </tr>
        <tr>
            <td>R22022</td>
            <td colspan="6" style="text-align:center;">2022.2.511</td>
        </tr>
        <tr>
            <td>R22022SP1</td>
            <td colspan="6" style="text-align:center;">2022.2.622</td>
        </tr>
        <tr>
            <td>R32022</td>
            <td colspan="6" style="text-align:center;">2022.3.913</td>
        </tr>
    </tbody>
</table>
</p>

<p id="jQuery">
<table class="Tbl k-table">
    <colgroup>
        <col width="50%" />
        <col width="50%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="6" style="color:white;text-align:center;background-color:#70757d;font-weight:bold;text-align:left;">Kendo UI for jQuery<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R32021</td>
            <td colspan="6" style="text-align:center;">2021.3.914</td>
        </tr>
        <tr>
            <td>R12022</td>
            <td colspan="6" style="text-align:center;">2022.1.119</td>
        </tr>
        <tr>
            <td>R12022SP1</td>
            <td colspan="6" style="text-align:center;">2022.1.301</td>
        </tr>
        <tr>
            <td>R22022</td>
            <td colspan="6" style="text-align:center;">2022.2.510</td>
        </tr>
        <tr>
            <td>R22022SP1</td>
            <td colspan="6" style="text-align:center;">2022.2.621</td>
        </tr>
        <tr>
            <td>R32022</td>
            <td colspan="6" style="text-align:center;">2022.3.913</td>
        </tr>
    </tbody>
</table>
</p>


<script type="text/javascript">
        function showHideRow(row) {
            $("#" + row).toggle();
            $('#expand'+row[row.length-1]).text(function (i, oldText) {
        return $.trim(oldText) == 'Click to expand the list of translators' ? 'Collapse' : 'Click to expand the list of translators';
		});
        }
</script>

<style>
    #Angular .hidden_row {
            display: none;
        }
</style>

<table class="Tbl k-table" id="Angular">
    <colgroup>
        <col width="30%" />
        <col width="70%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="2" style="color:white;text-align:center;background-color:#70757d;font-weight:bold;text-align:left;">Kendo UI for Angular</td>
        </tr>
    </thead>
    <tbody>
        <tr onclick="showHideRow('hidden_row1');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R32021</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand1">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row1" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                            <col width="34%" />
                            <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">5.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">6.3.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">5.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">5.1.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">5.4.0</td>
                        </tr>                        
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">5.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">7.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">1.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.3.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">7.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.3.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">5.1.1</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr onclick="showHideRow('hidden_row2');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R12022</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand2">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row2" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                        <col width="34%" />
                        <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">7.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">8.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">3.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">8.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.4.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">6.0.0</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr onclick="showHideRow('hidden_row3');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R12022SP1</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand3">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row3" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                        <col width="34%" />
                        <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">7.0.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">6.0.2</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">6.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">6.1.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">8.0.7</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">3.0.2</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.5.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">8.0.7</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">6.5.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">6.0.2</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr onclick="showHideRow('hidden_row4');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R22022</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand4">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row4" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                        <col width="34%" />
                        <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">8.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">9.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">4.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">9.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.0.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.0.0</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr onclick="showHideRow('hidden_row5');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R22022SP1</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand5">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row5" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                        <col width="34%" />
                        <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.2</td>
                        </tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">8.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.2</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.1.2</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.0.2</td>
                        </tr>
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">7.2.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">9.0.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">4.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.1.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">9.0.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.1.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.1.2</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr onclick="showHideRow('hidden_row6');">
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R32022</td>
            <td style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;cursor: pointer;"><span id="expand6">Click to expand the list of translators</span></td>
        </tr>
        <tr id="hidden_row6" class="hidden_row">
            <td colspan=4>
                <table>
                    <colgroup>
                        <col width="33%" />
                        <col width="34%" />
                        <col width="33%" />
                    </colgroup>
                    <thead>
                        <tr>
                            <td style="font-weight:bold;text-align:left;">Translator Name</td>
                            <td style="font-weight:bold;text-align:left;">Component Name</td>
                            <td style="font-weight:bold;text-align:center;">Component Version</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>KendoAngularAutoComplete</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.2.0</td>
                        </tr>
                            <td>KendoAngularButton</td>
                            <td>kendo-angular-buttons</td>
                            <td colspan="6" style="text-align:center;">8.1.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularComboBox</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.2.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDialog</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.1.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularDropdownList</td>
                            <td>kendo-angular-dropdowns</td>
                            <td colspan="6" style="text-align:center;">7.2.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularGrid</td>
                            <td>kendo-angular-grid</td>
                            <td colspan="6" style="text-align:center;">7.3.1</td>
                        </tr>
                        <tr>
                            <td>KendoAngularInputs</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">10.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPager</td>
                            <td>kendo-angular-pager</td>
                            <td colspan="6" style="text-align:center;">4.0.5</td>
                        </tr>
                        <tr>
                            <td>KendoAngularPanelBar</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.1.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularSwitch</td>
                            <td>kendo-angular-inputs</td>
                            <td colspan="6" style="text-align:center;">10.0.0</td>
                        </tr>
                        <tr>
                            <td>KendoAngularTabStrip</td>
                            <td>kendo-angular-layout</td>
                            <td colspan="6" style="text-align:center;">7.1.3</td>
                        </tr>
                        <tr>
                            <td>KendoAngularWindow</td>
                            <td>kendo-angular-dialog</td>
                            <td colspan="6" style="text-align:center;">7.1.3</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

## Available Translators

The __Available Translators__ section lists __all built-in translators__ that are currently available in Test Studio. All translators are enabled by default, which is the __recommended setup__. Each of the built-in translators can be disabled and not used while recording and executing tests, but we strongly advise you to contact the Test Studio Support Team prior to applying changes to the enabled translators.

![Available Translators][3]

[1]: images/translators/fig1.png
[2]: images/translators/fig2.png
[3]: images/translators/fig3.png