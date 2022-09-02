---
title: Mouse Actions
page_title: Quick Mouse Actions
description: "Test Studio Compact Recorder: Add mouse action steps from the Highlighting menu while recording Test Studio tests. Choose among left single or double mouse click, right mouse click. Add a mouse step to hover over an element."
position: 2
---
# Quick Mouse Actions

The __Quick Mouse Actions__ section in the Highlighting menu allows you to add different type of desktop mouse actions like right or double clicks and hover over an element.

![Quick Mouse Action Steps][1]

- [General notes](#general-notes)
- [Add a mouse action step](#add-a-desktop-mouse-action-step-in-recording-mode)
- [Add a mouse action step without recording](#create-a-click-step-without-recording-session)

## General Notes

In the general case __Test Studio Compact Recorder__ detects the click and type actions automatically during a recording session and adds the corresponding steps into the test - _'Click an element'_ or _'Type text into element'_. So, often you may not need to use the __Mouse Actions__ from the Highlighting menu for an ordinary click on an element in the application.

But the __Mouse Actions__ are very useful if you need to include a __double left click__, a __right click__ or you need to __hover over__ an element to activate its functionality.

## Add a Desktop Mouse Action Step in Recording Mode

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/" target="_blank">Telerik official page</a>.

2.&nbsp; If the recording browser window is large enough (it behaves differently if the browser window is shrunk) the __All Products__ list appears after you hover over it with the mouse. To automate the scenario you need to add a __Mouse HoverOver Step__.

![Add HoverOver Step][2]

3.&nbsp; Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the desktop action step and allow you to change the command type or offset position of the click point.

![Step Properties][3]

## Create a Click Step without Recording Session

Automated test maintenance may require adding new steps in an existing test. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional steps.

For the cases when the project and scenarios are quite complex, you can __add action steps for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; You can choose adding a click step from the __Quick Actions__ list or from the __Mouse Actions__ list. Select the step you need and click the **Add Step** button to insert the step in the test.

![Step Builder Quick actions][4]

![Step Builder Mouse actions][5]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

[1]: /img/features/recorder/highlighting-menu/mouse-actions/fig1.png
[2]: /img/features/recorder/highlighting-menu/mouse-actions/fig2.png
[3]: /img/features/recorder/highlighting-menu/mouse-actions/fig3.png
[4]: /img/features/recorder/highlighting-menu/mouse-actions/fig4.png
[5]: /img/features/recorder/highlighting-menu/mouse-actions/fig5.png

