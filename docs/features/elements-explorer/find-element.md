---
title: Find Element
page_title: Find Element
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/elements-pane-overview/find-element.aspx, /user-guide/elements-pane-overview/find-element
position: 3
---
# Change How an Element Is Found

When an action is recorded against an element from a web page or WPF application, or an element is explicitly added to the Elements repository from the DOM explorer, Test Studio generates a **Find Expression**, which then uses to locate that element during execution. 

In certain scenarios the automatically generated find expression may be ineffective, because locates multiple elements on the active window, or may use dynamically generated attributes, which are unreliable by the next test execution. In such cases you may require to adjust the find expression manually, so that it reflects the specifics of the application under test.

## Version 2019 R1 and Later

### Edit the Find Expression of an Element

To verify what find expression for an element was automatically generated and edit it, if necessary, use the <a href="/features/elements-explorer/overview#element-context-menu" target="_blank">Element's Explorer context menu</a> or double click on the same element.

<table id="no-table">
<tr>
<td>![Edit Element][101]</td>
<td>![Edit Element Double Click][102]</td>
</tr>
<table>

### Edit Element Pane

Each element selected for edit will be opened as a separate tab in the test pane. That way you can open multiple elements to edit and compare their attributes and find expressions. 

![Element's Pane][103]

To open another element to edit, switch back to the active test and the recorded elements will be listed again in the Element's Explorer. 

![Open second Element][104]

### Options in Element Pane without Active Recording Session

When there is no active recording session, the *Edit Element* pane displays the currently used find expression for the element and allows you to modify it. However, there are no avaialble suggestions based on the DOM tree and the modifed expression cannot be validated.

***Save*** and ***Reset*** buttons get enabled once there is any change in the find expression. Once the changes in the element are saved, these cannot be reverted and ***Reset*** button gets automatically disabled.

![Save/Reset][105]

If the modified element is being used from multiple steps, pressing the ***Save*** button triggers a dialog to select the tests or steps for which the find expression needs to be changed.

![Select steps][106]

Using the ***plus sign*** and ***recycle bin*** icons in the find expression field, you can add/delete filters to target different element's properties.

![Add/Delete Filter][107]

From the *Edit Element* pane you can start a recording session choosing between:

![Start recording session][108]

- ***Launch Recorder*** button - this will navigate to the URL set in the test (using the set preferred browser or will prompt you to choose a browser) or will launch a new instance of the WPF application under test.

- ***Run to Test Step*** button - this will execute the test to the step in which the element is being used. If there are multiple steps using the same element, a dialog appears to select the desired step to execute to.

![Select step to execute to][109]

- ***Choose Active Recorder*** dropdown - this dropdown will list any browser with active recording session. If this is empty, there is no application started in record mode. 

![Choose Active Recorder][110]

### Options in Element Pane with Active Recording Session

If the test was executed to a step, where the element exists on the page, it will be highlighted once the recorder is attached to the browser (the recorder is automatically paused to avoid recording any unnecessary steps).

In the *Eidt Element* pane are displayed the suggested properties of the element and the DOM tree of the current page.

![Edit in Live][111]

The DOM explorer in the *Eidt Element* pane provides its standard options from the <a href="/features/recorder/dom-explorer#context-menu" target="_blank">context menu</a>.

![DOM explorer][112]

If the elements find expression is not correct, but the element can be found by its backup search, an informational message appears to allow you to update the filters to use that backup search criteria to locate the element and list the recommended filters to use.

![Update Filter][113]

Hover over the info icon next to the button to see what is the backup search for that element.

![Backup Search][114]

If the element cannot be found in the current page with attached recorder, there will be an informational message stating the same. 

![Element Not found][115]

Use the ***Validate Expression*** button to validate the changed find expression filters.

![Validate Expression][116]

***Advanced Mode*** button displays the current find expression and allows you to type in a custom one. Click the button once again to switch back to filters view.

![Advanced Mode][117]

### Data Driven Find Expression

The find expression of the elements can be data driven to extend the execution and reuse of tests and elements. To be able to data drive an element, you need to <a href="/features/data-driven-testing/add-data-source" target="_blank">add a data source</a> and <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">bind it to the test</a>, which uses the element. 

The find expression builder will display the columns of the attached data source in a dropdown of the selected filters for the element. Once a column is selected, click the ***Set*** button to set this to be used in the filter.

![Select column to attach to filter][118]

A warning message appears that the element cannot be validated or troubleshooted unless the data binding is removed. To remove the data binding you can delete the data driven filter or re-record the element. 

![Warning message][119]

There are few specific scenarios when the names of variables will not be displayed in that view and their names need to be entered manually. These are

- a variable extracted either with an <a href="/features/recorder/verifications/extraction" target="_blank">extraction step</a> or <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">in code</a>.

- a column name from a data source of a parent test - in the cases when the current test is nested as a step and uses the parent test data source (see <a href="/features/data-driven-testing/multi-level-tests" target="_blank">further details for multi level tests</a>)

To filter an element's find expression using the column name from parent data source or the value of an extracted variable, enter its name in the *Add coded data variable* field (without the $ notation), click on the brackets and then the *Set* button. 

![Bind Coded variable][120]

## Version 2018 R3 and Earlier

When a web page element has an action recorded against it, or you explicitly add an element to the Elements pane, a **Find Expression** is generated that Test Studio uses to find that specific element on the web page.

To change how an element is found, right click on the element in the Explorer and select **Edit Element**.

![Edit Element][1]

In the VS plugin, click the **Show Element Explorer** icon in the toolbar and locate the Explorer at the bottom of the screen.

![Edit Element VS][2]

Select **Edit in Live** to directly open the <a href="#find-element">Find element</a> dialog for the page open in the current recorder.

![Edit in live][3]

The **Find Element** splash screen appears. You have three options for how to locate the element:

![Find Element][4]

**Find in the Live Version** - find the element using the latest version of a new browser window, an existing test step, or an application that you currently have open.

- **New Browser** - this will launch a new instance of your application. You may need to manually navigate to the element. Click **Browse & Navigate** to proceed.
- **Existing Test Step** - use an existing step from a test to get to the element. Click **Choose Test Step** to proceed.
- **Current Page** - select where the element is available from a list of currently running browser instances or WPF applications. Click **Go** to proceed.

![Find Element][5]

**Find in the Cached Version** - if your test failed, you can find the element using the cached version of the application at the time of failure. Accessible only through the **Resolve Failure** tab in the Step Failure Details.

**Find Without Connection** - choose this option to find the element without connecting to the application.

> To skip this splash screen the next time you load the Find Element dialog, check the box at the bottom and click Close.

The <a name="find-element">Find Element</a> dialog appears. The Element Name, Element Type, and Connection Status are at the top.

![Find Element][6]

The **Change Element** link opens the **Select New Element dialog**.

![Change Element][7]

In the Select Html Element dialog, you can open the Find Element dialog for a different element in the Elements Repository.

![Select HTML Element][8]

The **Connection Options** button takes you back to the **Find Element** splash screen.

![Connection Options][9]

**The Suggestions and DOM** views are on the left side.

- **Suggestions** - these are the suggested items to help you find the element in the application. Click an item to add it to your **Find Settings**. 

![Suggestions][10]

- **DOM** - use the DOM as a reference when creating your Find Settings. This view is helpful in determining where your element is located relative to the DOM tree. 

![DOM][11]

The **Find Settings** view is on the right side. You can edit these settings by typing in new properties, selecting a new modifier in the drop-down menu, or changing the values. Click Validate to confirm whether the element can be found using the current Find Settings.

<table id="no-table">
<tr>
<td>![Element Found][12]</td>
<td>![Element Not Found][13]</td>
</tr>
<table>

### Data-driven find logic

<a name="data-driven"></a>Here, you can also <a href="/features/data-driven-testing/overview" target="_blank">data drive</a> the element find expression. If your test has an attached data source, the value fields of the find expressions for your elements will include a drop-down list displaying columns from your data source.

![Data drive find exp][14]

electing a column databinds the column to the value of the find expression rule.

![Data drive find exp][15]

If the element was not found, click the **Troubleshoot** button. Choose a suggested fix from the Troubleshoot screen.

![Troubleshoot][16]

There are three additional buttons in the upper right of the **Find Element** dialog:

![Additional Buttons][17]

- **Select New Element** - choose this option if the incorrect element was selected for this step. This will clear your current settings and <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> provides new filters for the new element. 

![Select New Element][18]

- **Advanced** - edit the Find Settings using a string-based expression builder. 

![Advanced][19]

- **Reset** - restores fields to their original settings. 

![Reset][20]

Once you've confirmed you are targeting the correct element and it is correctly found, click Save and Close. If the modified element is used by multiple automation steps, you are prompted to select the steps you want to persist changes to.

![Test Case Selector][21]

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
[104]: /img/features/elements-explorer/find-element/fig104.png
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