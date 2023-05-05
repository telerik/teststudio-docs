---
title: Blank Step Builder Pane 
page_title: Blank Step Builder Pane in Visual Studio
description: "Test Studio plugin in Visual Studio is installed but Step Builder and Elements Explorer are blank. I can't select steps or elements to add in the test. Test Studio plugin in Visual Studio not working properly"
position: 1
---
# Blank Step Builder and Elements Explorer Panes in Visual Studio

## PROBLEM

Test Studio plugin in Visual Studio is installed successfully and I can create a project and record tests. When I try to see the elements used in the recorded steps in the Elements Explorer or add steps through the Step Builder, these two panes are empty and display no options.

## SOLUTION

The Test Studio Step Builder and Elements Explorer panes are affected by a common issue for various extensions in Visual Studio 2019 and 2022. It is related to how Visual Studio optimizes rendering, which is a setting in the product.

Follow the below steps to turn off the aforementioned Visual Studio project option and enable the Test Studio panes normal appearance.

1.&nbsp; Open Visual Studio.

2.&nbsp; Open __Tools-> Options__ menu.

3.&nbsp; On the left hand side expand __Environment__  section and open the __General__ section.

4.&nbsp; On the right hand side of the _Options_ window are listed all options in this section. Uncheck the __Optimize rendering for screens with different pixel densities__.

5.&nbsp; Restart Visual Studio and start the Test Studio project.

![Optimize rendering option in Visual Studio](/img/troubleshooting-guide/visual-studio-tg/blank-step-builder/optimiseRenderingVS2019.png)