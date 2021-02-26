---
title: Modifying Elements Find Expression
page_title: Modifying Elements Find Expression
description: "Unable to find Element - Test Studio test failure. How to change how an element is located in Test studio test run/ execution. Update the elements find expression in Test Studio. How to adjust the proeprties used to locate an element in Test Studio."
previous_url: /user-guide/elements-pane-overview/find-element.aspx, /user-guide/elements-pane-overview/find-element
position: 2
---
# Modifying Element's Find Expression

In certain scenarios the automatically generated <a href="/features/elements-explorer/elements-find-expression" target="_blank">find expression</a> may be ineffective, because locates multiple elements on the active window, or may use dynamically generated attributes, which are unreliable by the next test execution. In such cases you may require adjusting the find expression manually, so that it reflects the specifics of the application under test.

## Edit the Find Expression of an Element

To verify what find expression for an element was automatically generated and edit it, if necessary, use the <a href="/features/elements-explorer/overview#element-context-menu" target="_blank">Element's Explorer context menu</a> or double click on the same element.

<table id="no-table">
	<tr>
		<td><img src="/img/features/elements-explorer/find-element/fig101.png" alt="Edit Element"></td>
		<td><img src="/img/features/elements-explorer/find-element/fig102.png" alt="Edit Element Double Click"></td>
	</tr>
</table>

## Edit Element Pane

Each element selected for edit will be opened as a separate tab in the test pane. That way you can open multiple elements to edit and compare their attributes and find expressions. 

![Element's Pane][103]

To open another element to edit, select any other element from the Element's Explorer.

## Options in Element Pane without Active Recording Session

When there is no active recording session, the *Edit Element* pane displays the currently used find expression for the element and allows you to modify it. However, there are no available suggestions based on the DOM tree and the modified expression cannot be validated.

***Save*** and ***Reset*** buttons get enabled once there is any change in the find expression. Once the changes in the element are saved, these cannot be reverted and ***Reset*** button gets automatically disabled.

![Save/Reset][105]

If the modified element is being used from multiple steps, pressing the ***Save*** button triggers a dialog to select the tests or steps for which the find expression needs to be changed.

![Select steps][106]

Using the ***plus sign*** and ***recycle bin*** icons in the find expression field, you can add/delete filters to target different element's properties.

![Add/Delete Filter][107]

From the **Edit Element** pane you can start a recording session choosing between:

![Start recording session][108]

- ***Launch Recorder*** button - this will navigate to the URL set in the test (using the set preferred browser or will prompt you to choose a browser) or will launch a new instance of the WPF application under test.

- ***Run to Test Step*** button - this will execute the test to the step in which the element is being used. If there are multiple steps using the same element, a dialog appears to select the desired step to execute to.

![Select step to execute to][109]

- ***Choose Active Recorder*** dropdown - this dropdown will list any browser with active recording session. If this is empty, there is no application started in record mode.

![Choose Active Recorder][110]

## Options in Element Pane with Active Recording Session

If the test was executed to a step, where the element exists on the page, it will be highlighted once the recorder is attached to the browser (the recorder is automatically paused to avoid recording any unnecessary steps).

In the *Edit Element* pane are displayed the suggested properties of the element and the DOM tree of the current page.

![Edit in Live][111]

The DOM explorer in the *Edit Element* pane provides its standard options from the <a href="/features/recorder/dom-explorer#context-menu" target="_blank">context menu</a>.

![DOM explorer][112]

If the elements find expression is not correct, but the element can be found by its backup search, an informational message appears to allow you to update the filters to use that backup search criteria to locate the element and list the recommended filters to use.

![Update Filter][113]

Hover over the info icon next to the button to see what is the backup search for that element.

![Backup Search][114]

If the element cannot be found in the current page with attached recorder, there will be an informational message stating the same. 

![Element Not found][115]

Use the **Validate Expression** button to validate the changed find expression filters.

![Validate Expression][116]

## Elements Image Settings

The ***Image Settings*** button switches the view in the Elements pane and provides details for the currently recorded image corresponding to that element. Read further <a href="/features/elements-explorer/find-element-by-image" target="_blank">**details for the Elements Image Settings**</a>.

![Switch to Elements Image Settings][130]

## Advanced Mode

**Advanced Mode** button displays the current find expression in text format and allows you to type in a custom one.

![Advanced Mode][117]

Below is a list of the optional supported operators, when building custom find expressions. Keep in mind that, when used, the operator is always the first character after the equal sign (=). The operator special character can be escaped with preceding apostrophe ('), if it is meant to be interpreted as a literal character.

<table class="docs">
<tr>
	<th>Leading character</th><th>Example</th><th>Description</th>
</tr>
<tr>
	<td>~</td>
	<td>foo=~bar</td>
	<td>Find the element where attribute foo 'contains' bar</td>
</tr>
<tr>
	<td>!</td>
	<td>foo=!bar</td>
	<td>Find the element where attribute foo 'does not contain' bar</td>
</tr>
<tr>
	<td>^</td>
	<td>foo=^bar</td>
	<td>Find the element where attribute foo 'starts with' bar</td>
</tr>
<tr>
	<td>?</td>
	<td>foo=?bar</td>
	<td>Find the element where attribute foo 'ends with' bar</td>
</tr>
<tr>
	<td>#</td>
	<td>foo=#ba*</td>
	<td>Find the element where attribute foo 'matches the regular expression' ba* - See this link for a description of regular expressions.</td>
</tr>
<tr>
	<td>|</td>
	<td>'id=CenterDiv', '|', 'tagIndex=a:2' </td>
	<td>Chains two expressions together. Chained expressions work by finding the element that matches the first expression, then underneath that find the element that matches the next expression. There is no technical limit to how many expressions can be chained together. The example tells <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> to find the first element whose ID = CenterDiv and then under that element find the third anchor element (tagIndex is 0 based).</td>
</tr>
<tr>
	<td>'</td>
	<td>textContent=''City</td>
	<td>Escape special characters. Find the element whose text = 'City', including the ' characters. </td>
</tr>
<tr>
	<td>+</td>
	<td>foo=+</td>
	<td>Find the element that has the specified attribute. Find the element that has the attribute 'foo'.</td>
</tr>
<tr>
	<td>-</td>
	<td>foo=-</td>
	<td>Find the element that does not have the specified attribute. Find the element that does not have the attribute 'foo'.</td>
</tr>
</table>

## Data Driven Find Expression

The find expression of the elements can be data driven to extend the execution and reuse of tests and elements. To be able to data drive an element, you need to <a href="/features/data-driven-testing/add-data-source" target="_blank">add a data source</a> and <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">bind it to the test</a>, which uses the element. 

The find expression builder will display the columns of the attached data source in a dropdown of the selected filters for the element. Once a column is selected, click the ***Set*** button to set this to be used in the filter.

![Select column to attach to filter][118]

A warning message appears that **the find by image operation will not be performed and the element cannot be validated or troubleshoot unless the data binding is removed**. To remove the data binding you can delete the data driven filter or re-record the element.

![Warning message][119]

There are few specific scenarios when the names of variables will not be displayed in that view and their names need to be entered manually. These are

- a variable extracted either with an <a href="/features/recorder/verifications/extraction" target="_blank">extraction step</a> or <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">in code</a>.

- a column name from a data source of a parent test - in the cases when the current test is nested as a step and uses the parent test data source (see <a href="/features/data-driven-testing/multi-level-tests" target="_blank">further details for multi level tests</a>)

To filter an element's find expression using the column name from parent data source or the value of an extracted variable, enter its name in the *Add coded data variable* field (without the $ notation), click on the brackets and then the *Set* button.

![Bind Coded variable][120]

[1]: /img/features/elements-explorer/find-element/fig1.png
[2]: /img/features/elements-explorer/find-element/fig2.png
[3]: /img/features/elements-explorer/find-element/fig3.png
[4]: /img/features/elements-explorer/find-element/fig4.png
[5]: /img/features/elements-explorer/find-element/fig5.png
[6]: /img/features/elements-explorer/find-element/fig6.png
[7]: /img/features/elements-explorer/find-element/fig7.png
[8]: /img/features/elements-explorer/find-element/fig8.png
[9]: /img/features/elements-explorer/find-element/fig9.png
[10]: /img/features/elements-explorer/find-element/fig10.png
[11]: /img/features/elements-explorer/find-element/fig11.png
[12]: /img/features/elements-explorer/find-element/fig12.png
[13]: /img/features/elements-explorer/find-element/fig13.png
[14]: /img/features/elements-explorer/find-element/fig14.png
[15]: /img/features/elements-explorer/find-element/fig15.png
[16]: /img/features/elements-explorer/find-element/fig16.png
[17]: /img/features/elements-explorer/find-element/fig17.png
[18]: /img/features/elements-explorer/find-element/fig18.png
[19]: /img/features/elements-explorer/find-element/fig19.png
[20]: /img/features/elements-explorer/find-element/fig20.png
[21]: /img/features/elements-explorer/find-element/fig21.png
[101]: /img/features/elements-explorer/find-element/fig101.png
[102]: /img/features/elements-explorer/find-element/fig102.png
[103]: /img/features/elements-explorer/find-element/fig103.png
[104]: /img/features/elements-explorer/find-element/fig104.gif
[105]: /img/features/elements-explorer/find-element/fig105.png
[106]: /img/features/elements-explorer/find-element/fig106.png
[107]: /img/features/elements-explorer/find-element/fig107.png
[108]: /img/features/elements-explorer/find-element/fig108.png
[109]: /img/features/elements-explorer/find-element/fig109.png
[110]: /img/features/elements-explorer/find-element/fig110.png
[111]: /img/features/elements-explorer/find-element/fig111.png
[112]: /img/features/elements-explorer/find-element/fig112.png
[113]: /img/features/elements-explorer/find-element/fig113.png
[114]: /img/features/elements-explorer/find-element/fig114.png
[115]: /img/features/elements-explorer/find-element/fig115.png
[116]: /img/features/elements-explorer/find-element/fig116.png
[117]: /img/features/elements-explorer/find-element/fig117.png
[118]: /img/features/elements-explorer/find-element/fig118.png
[119]: /img/features/elements-explorer/find-element/fig119.png
[120]: /img/features/elements-explorer/find-element/fig120.png
[130]: /img/features/elements-explorer/find-element/fig130.png