---
title: Asp.NET Test Region Control
page_title: Asp.NET TR Control
description: "Using TestRegions in Test Studio Testing Framework tests. Example of using TestRegions in coded tests. "
position: 2
---
#Using Asp.Net TestRegion Control#

TestRegions can be a powerful tool to build testability into your web applications and enable your test automation teams to build highly resilient test beds that have low maintenance costs compared to the traditional automation methods like the HTTP record/replay approaches. TestRegions are ideal to be used with dynamic web frameworks like ASP.NET since they can take out some of the complexity that comes with the auto generated html. Given that TestRegions are injected in the source code of web pages, we wanted to provide Visual Studio and ASP.NET developers a richer experience at design time. Telerik Testing Framework includes an ASP.NET TestRegion Custom Control that can be used just like any other asp: control to define TestRegion's into your code. This control allows you to:

* Visually view the defined TestRegions in your app directly in Visual Studio's design view. See figure below.

* At runtime this control renders as an HTML comment (), so you don't need to worry about this control affecting your application's markup or layout which is a core principle in the initial design of TestRegions.

![AspNetApp][1]

Below is a segment of the HTML persisted that is shown in design view above.

![HTML][2]

**Note:** The samples shown above are included in full in the code samples installed with Telerik Testing Framework.

##Adding ASP.NET TestRegion Control to Your Toolbox##

To be able to use this control as shown above, you simply need to add it first to your ToolBox. Visual Studio should handle all tag registrations once you drag-n-drop the control on your pages. To add the control to your toolbox:

1. Locate the ArtOfTest.WebAii.AspNet.dll on your machine. The dll should be located in your Telerik Testing Framework %InstallDir%. This dll contains the ASP.NET TestRegion control and will contain any future test controls we might introduce for ASP.NET.

2. In Visual Studio, open the Toolbox. (View->Toolbox)

3. Right-Click in your Toolbox and select 'Add Tab'.

4. A new tab on your Toolbox will be created. Name it "Testing Controls" or any other title you might choose.

5. Inside the new tab, right-click again and this time select "Choose Items...". This will pop-up the 'Choose Toolbox Items' dialog.

	![Choose Toolbox Items][3]

6. Click on 'Browse' button and navigate to the ArtOfTest.WebAii.AspNet.dll that you located in step 1 above. Select it and click 'Open'. The control should be added to the dialog.

	
	![Browser][4]

7. Now your control is added to your Toolbox and should be ready to be used.

	![TestRegion][5]


[1]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control/fig1.png
[2]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control/fig2.png
[3]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control/fig3.png
[4]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control/fig4.png
[5]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/test-regions-wtc/asp-net-tr-control/fig5.png


