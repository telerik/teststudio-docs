---
title: Modifying Elements Find Expression
page_title: Modifying Elements Find Expression (Archive)
description: "Archived element find expressions and how to change this"
position: 0
---
# (Archive) Element's Find Expressions

In certain scenarios the automatically generated <a href="/features/elements-explorer/elements-find-expression" target="_blank">find expression</a> may be ineffective, because locates multiple elements on the active window, or may use dynamically generated attributes, which are unreliable by the next test execution. In such cases you may require adjusting the find expression manually, so that it reflects the specifics of the application under test.

## Version 2018 R3 and Earlier (Both Standalone Application and Visual Studio Plugin)

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

## Data-driven find logic

<a name="data-driven"></a>Here, you can also <a href="/features/data-driven-testing/overview" target="_blank">data drive</a> the element find expression. If your test has an attached data source, the value fields of the find expressions for your elements will include a drop-down list displaying columns from your data source.

![Data drive find exp][14]

Selecting a column data binds the column to the value of the find expression rule.

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