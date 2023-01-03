---
title: Elements Mapping (IntelliMap)
page_title: Elements Mapping (IntelliMap) - Test Studio Dev Documentation
description: Test Studio Dev IntelliMap allows you to easily map the predefined elements to the actual one once the application UI is ready for test. 
position: 3
---
# Elements Mapping (IntelliMap)

Once your application is ready for testing you can map your <a href="/features/elements-explorer/predefined-elements" target="_blank">predefined elements</a> to the actual elements. In order to proceed select the predefined element you would like to map and select Element Mapping button:

<table id="no-table">
	<tr>
		<td>!![Element Mapping TS][6] <br><br>**Standalone version**</td>
		<td>![Element Mapping TS][15] <br><br>**VS plugin**</td>
	</tr>
<table>


The mapping dialog window appears allowing you to select between a Web or WPF test.

* For Web: type New URL or choose from Recent URLs and click **Start Mapping** button. 
* For WPF: select new WPF app using the browse button or choose from Recent Apps and click **Start Mapping** button.

<table id="no-table">
<tr>
<td>![Web][7] <br><br>**Web**</td>
<td>![WPF][8] <br><br>**WPF**</td>
<tr>
<table>

> The example shown here is for a Web test, but for a WPF test the actions are exactly the same.

Select Recording browser and click **Record**. 

![Choose Recording Browser][9]

Test Studio will navigate to the URL, attach the recorder and enable Highlighting so you can directly highlight the desired element and click on **Select Element** as shown below:


![Select Element][10]

You select the predefined element you would like to map (1) from the Elements section, confirm the find logic (2) and click on Map Element button (3).

![Map Element][11]

> Please note in the example above we are working with only one predefined element in the Elements section. However you can have many predefined elements listed there. You need to be careful when mapping with an actual element which predefined element is selected. In order to avoid confusion it will be best to use descriptive friendly names to your predefined elements.

In case you would like to build more robust find logic before mapping the predefined element you can add an **Expression Item**.

![Add Expression Item][12]

Another filter is added so you can tweak the element's find logic.

![find logic][13]

You can undo all the changes and revert to the default find expression using the **Restore Default Expression** button.

![Restore Default Expression][14]

<br>
<br>

* See Also: <a href="/features/elements-explorer/predefined-elements" target="_blank">Predefined elements</a>

[6]: images/element-mapping/fig6.png
[7]: images/element-mapping/fig7.png
[8]: images/element-mapping/fig8.png
[9]: images/element-mapping/fig9.png
[10]: images/element-mapping/fig10.png
[11]: images/element-mapping/fig11.png
[12]: images/element-mapping/fig12.png
[13]: images/element-mapping/fig13.png
[14]: images/element-mapping/fig14.png
[15]: images/element-mapping/fig15.png
