---
title: Scroll Actions
page_title: Scroll Actions
description: "Test Studio Compact Recorder: Add scroll action steps from the Highlighting menu while recording Test Studio tests. Choose among scrolling Element to top of the page, the center of the page, or the bottom of the page. Scroll element to make it visible on page."
position: 3
---
# Scroll Actions

The __Scroll Actions__ section in the Highlighting menu allows you to add different type of scroll actions. Scroll action steps help you move the target element within the visible part of the tested application.

![Scroll Action Steps][1]

- [General notes](#general-notes)
- [Add a scroll step](#add-a-scroll-step-in-recording-mode)
- [Add a scroll step without recording](#create-a-scroll-step-without-recording-session)

## General Notes

The action steps in a Test Studio automated scenario include scrolling of the target element out-of-the-box. However, there are scenarios in which you need to verify the element state without interacting with it and the __Scroll Actions__ can help to accomplish this.

The options for scrolling are:

- **To Page Top** - target element is positioned in the top of the window.

- **To Page Bottom** - target element is positioned in the bottom of the window.

- **To Page Center** - target element is positioned in the center of the window.

## Add a Scroll Step in Recording Mode

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/" target="_blank">Telerik official page</a>.

2.&nbsp; This sample scenario scrolls the __Download DevCraft Trial__ button to the top of the page to reveal part of the page under. Enable the highlighting and hold the mouse over the button - choose the __Scroll to Page Top__ and add the step.

![Add scroll step][2]

## Create a Scroll Step without Recording Session

Automated test maintenance may require adding new steps in an existing test. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional steps.

For the cases when the project and scenarios are quite complex, you can __add scroll steps for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; You can choose adding a click step from the __Quick Actions__ list or from the __Scroll Actions__ list. Select the step you need and click the **Add Step** button to insert the step in the test.

![Step Builder Scroll actions][3]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

[1]: /img/features/recorder/highlighting-menu/scroll-actions/fig1.png
[2]: /img/features/recorder/highlighting-menu/scroll-actions/fig2.png
[3]: /img/features/recorder/highlighting-menu/scroll-actions/fig3.png

