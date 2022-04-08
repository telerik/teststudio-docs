---
title: Translators Project Settings
page_title: Translators Project Settings
description: "Test Studio comes with built-in translators for the Telerik components. Test Studio provides Basic translators for HTML, Silverlight, and WPF, and translators built specifically for Telerik AJAX and Silverlight RadControls, KendoUI for jQuery and KendoUI for Angular, Telerik UI for Blazor"
position: 8
---

<script>
window.addEventListener('DOMContentLoaded', function () {
$(".toggle_container").hide();
    
    $("p.trigger").click(function(e){
        e.preventDefault();
        $(this).toggleClass("active").next().slideToggle("normal");
		$(this).find('#d').text(function (i, oldText) {
        return $.trim(oldText) == '+' ? '-' : '+';
		});
		
    });
    });
</script>

# Translators Project Settings

The <a href="/getting-started/test-recording/translators" target="_blank">built-in translators</a> are extensions that open up an element to work with Test Studio and thus allow interaction with the Elements Menu  exposing a rich set of verification tasks.

This section of the <a href="/features/project-settings/overview" target="_blank">Project Settings</a> allows you to adjust the version of the Telerik and Kendo UI components used to build the application under test and lets Test Studio apply the matching translators. From this menu you can review and enable/disable the components for which a translator is available.

![Translators Project Settings][1]

## Select the Version of the Telerik Components under Test

The __Telerik Components Under Test__ section lets you instruct the translators' version to match the version of the UI components in the tested page for this project. This setting applies to both the recording and execution flows and allows you to smoothly create tests and run these for various applications.

![Telerik Components Under Test Version][2]

<p><hr></p>
<p></p>

<p class="trigger"><a name="TS Mapping to UI Components" style="color:black; text-decoration: none;font-size: 22px;line-height: 1em;font-weight: 400;letter-spacing: -0.02em;";> Test Studio Mapping to UI Components Versions <span id="d" style="color:black";> + </span></a></p>

<div class="toggle_container">
<div class="block">

<hr/>
<br>

<a name="How to Know Which Version to Choose" style="color:black; text-decoration: none;font-size: 22px;line-height: 1em;font-weight: 400;letter-spacing: -0.02em;";>How to Know Which is the Version of Components Used in the Tested Page?</a>

<p>
As Quality Assurance Engineer you often don't know what type and version of UI components was used to create the application you need to automate. And since there is no convenient way to identify the version of the components in an already built and deployed application, the most reliable approach is to contact the development team and discuss the topic internally.
</p>
In the below grid you can find the versions of the UI components matching the translators versions from the list.
<p>
</p>
<p>
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
    </tbody>
</table>
</p>
<p>
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
    </tbody>
</table>
</p>
<p>
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
    </tbody>
</table>
</p>


<p>
<table class="Tbl k-table">
    <colgroup>
        <col width="50%" />
        <col width="50%" />
    </colgroup>
    <thead>
        <tr>
			<td colspan="6" style="color:white;text-align:center;background-color:#70757d;font-weight:bold;text-align:left;">Kendo UI for Angular<td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="6" style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R32021</td>
        </tr>
        <tr>
            <td>kendo-angular-buttons</td>
            <td colspan="6" style="text-align:center;">6.3.0</td>
        </tr>
        <tr>
            <td>kendo-angular-charts</td>
            <td colspan="6" style="text-align:center;">5.3.0</td>
        </tr>
        <tr>
            <td>kendo-angular-common</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-dateinputs</td>
            <td colspan="6" style="text-align:center;">5.2.3</td>
        </tr>
        <tr>
            <td>kendo-angular-dialog</td>
            <td colspan="6" style="text-align:center;">5.1.1</td>
        </tr>
        <tr>
            <td>kendo-angular-dropdowns</td>
            <td colspan="6" style="text-align:center;">5.4.0</td>
        </tr>
        <tr>
            <td>kendo-angular-excel-export</td>
            <td colspan="6" style="text-align:center;">4.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-grid</td>
            <td colspan="6" style="text-align:center;">5.4.0</td>
        </tr>
        <tr>
            <td>kendo-angular-grid</td>
            <td colspan="6" style="text-align:center;">5.4.0</td>
        </tr>
        <tr>
            <td>kendo-angular-icons</td>
            <td colspan="6" style="text-align:center;">0.4.3</td>
        </tr>
        <tr>
            <td>kendo-angular-inputs</td>
            <td colspan="6" style="text-align:center;">7.4.0</td>
        </tr>
        <tr>
            <td>kendo-angular-label</td>
            <td colspan="6" style="text-align:center;">3.1.0</td>
        </tr>
        <tr>
            <td>kendo-angular-layout</td>
            <td colspan="6" style="text-align:center;">6.3.0</td>
        </tr>
        <tr>
            <td>kendo-angular-popup</td>
            <td colspan="6" style="text-align:center;">4.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-progressbar</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-treeview</td>
            <td colspan="6" style="text-align:center;">5.2.0</td>
        </tr>
        <tr>
            <td colspan="6" style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R12022</td>
        </tr>
        <tr>
            <td>kendo-angular-buttons</td>
            <td colspan="6" style="text-align:center;">7.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-charts</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-common</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-dateinputs</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-data-query</td>
            <td colspan="6" style="text-align:center;">1.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-dialog</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-drawing</td>
            <td colspan="6" style="text-align:center;">1.9.3    </td>
        </tr>
        <tr>
            <td>kendo-angular-dropdowns</td>
            <td colspan="6" style="text-align:center;">6.0.0    </td>
        </tr>
        <tr>
            <td>kendo-angular-excel-export</td>
            <td colspan="6" style="text-align:center;">4.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-grid</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-icons</td>
            <td colspan="6" style="text-align:center;">0.4.5</td>
        </tr>
        <tr>
            <td>kendo-angular-inputs</td>
            <td colspan="6" style="text-align:center;">8.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-label</td>
            <td colspan="6" style="text-align:center;">3.1.2</td>
        </tr>
        <tr>
            <td>kendo-angular-layout</td>
            <td colspan="6" style="text-align:center;">6.4.0</td>
        </tr>
        <tr>
            <td>kendo-angular-pdf-export</td>
            <td colspan="6" style="text-align:center;">3.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-popup</td>
            <td colspan="6" style="text-align:center;">4.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-progressbar</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-treeview</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        <tr>
            <td colspan="6" style="color:white;text-align:center;background-color:#9ca3ad;font-weight:bold;text-align:left;">R12022SP1</td>
        </tr>
        <tr>
            <td>kendo-angular-buttons</td>
            <td colspan="6" style="text-align:center;">7.0.3<td>
        </tr>
        <tr>
            <td>kendo-angular-charts</td>
            <td colspan="6" style="text-align:center;">6.0.1</td>
        </tr>
        <tr>
            <td>kendo-angular-common</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-dateinputs</td>
            <td colspan="6" style="text-align:center;">6.0.2</td>
        </tr>
        <tr>
            <td>kendo-angular-data-query</td>
            <td colspan="6" style="text-align:center;">1.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-dialog</td>
            <td colspan="6" style="text-align:center;">6.0.2</td>
        </tr>
        <tr>
            <td>kendo-angular-drawing</td>
            <td colspan="6" style="text-align:center;">1.9.3</td>
        </tr>
        <tr>
            <td>kendo-angular-dropdowns</td>
            <td colspan="6" style="text-align:center;">6.0.1</td>
        </tr>
        <tr>
            <td>kendo-angular-excel-export</td>
            <td colspan="6" style="text-align:center;">4.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-grid</td>
            <td colspan="6" style="text-align:center;">6.1.0</td>
        </tr>
        <tr>
            <td>kendo-angular-icons</td>
            <td colspan="6" style="text-align:center;">1.0.1</td>
        </tr>
        <tr>
            <td>kendo-angular-inputs</td>
            <td colspan="6" style="text-align:center;">8.0.7</td>
        </tr>
        <tr>
            <td>kendo-angular-label</td>
            <td colspan="6" style="text-align:center;">3.1.3</td>
        </tr>
        <tr>
            <td>kendo-angular-layout</td>
            <td colspan="6" style="text-align:center;">6.5.1</td>
        </tr>
        <tr>
            <td>kendo-angular-pdf-export</td>
            <td colspan="6" style="text-align:center;">3.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-popup</td>
            <td colspan="6" style="text-align:center;">4.0.3</td>
        </tr>
        <tr>
            <td>kendo-angular-progressbar</td>
            <td colspan="6" style="text-align:center;">2.0.0</td>
        </tr>
        <tr>
            <td>kendo-angular-treeview</td>
            <td colspan="6" style="text-align:center;">6.0.0</td>
        </tr>
        </tbody>
</table>
</p>
<hr/>

</div>
</div>
<p></p>
<p></p>
<p></p>


## Available Translators

The __Available Translators__ section lists all built-in translators that are currently available in Test Studio. All translators are enabled by default, which is the recommended setup. Any of the built-in translators can be disabled and not used while recording and executing tests, but we strongly advise you to contact the Test Studio Support Team prior to applying changes to the enabled translators.

![Available Translators][3]

[1]: /img/features/project-settings/translators/fig1.png
[2]: /img/features/project-settings/translators/fig2.png
[3]: /img/features/project-settings/translators/fig3.png
