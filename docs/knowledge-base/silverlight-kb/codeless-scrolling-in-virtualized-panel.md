---
title: Codeless Scrolling in Virtualized Panel
page_title: Codeless Scrolling in Virtualized Panel
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Codeless Scrolling in Virtualized Panel


It may be necessary to scroll down through a control that uses a Silverlight virtualizing panel, because in Test Studio, only the rows presented in the Visual Tree can be tested. This is a limitation of the Visual Tree contained in the Silverlight engine. Silverlight puts into the Visual Tree only the UI components necessary to render the page on the screen. 

For example, for a grid that holds 100 rows of data but can only display 20 at a time, Silverlight typically will only put 22 rows of UI elements in the Visual Tree (20 visible plus one above and one below). The only way to get all 100 rows is to scroll down through the entire grid.


1.&nbsp; Hover over highlighting the element you want to scroll to. 

2.&nbsp; Select the translator for the **GridViewVirtualizingPanel**.

3.&nbsp; Select **Quick Steps -> Scroll Actions -> In Virtualized Panel**. 

![Scroll in virtualized panel][1]

4.&nbsp; This add a scroll step to the test step pane.

![Step added][2]

5.&nbsp; This step targets a virtualized panel element under the Silverlight application in the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

![Element in Elements Explorer][3]

[1]: /img/knowledge-base/silverlight-kb/codeless-scrolling-in-virtualized-panel/fig1.png
[2]: /img/knowledge-base/silverlight-kb/codeless-scrolling-in-virtualized-panel/fig2.png
[3]: /img/knowledge-base/silverlight-kb/codeless-scrolling-in-virtualized-panel/fig3.png
