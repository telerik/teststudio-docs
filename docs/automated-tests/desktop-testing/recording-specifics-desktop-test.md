---
title: Recording Desktop Tests
page_title: Recording Desktop Test
description: "Testing a desktop app with Test Studio. Specifics in recording desktop application scenarios in Test Studio. Record an automated scenario for desktop app in Test Studio. "
position: 1
---
# Recording Specifics for Dekstop Tests in Test Studio

Test Studio recording feature supports various desktop applications. Once a desktop test is configured for specific application you can start recording the automation scenarios.

> **Disclaimer**
> <br>
> <br>
> The Desktop test feature is officially __released with Test Studio R2 2022 (v.2022.2.727) in Beta__ stage. It supports basic recording features including highlighting and partial test execution, elements repository represented in the Elements Explorer and editing the recorded elements.

This article guides you through the specifics of recording steps in a desktop test.

- [Ready State for Desktop Recording](#recording-ready-state)
- [Highlighting Menu](#highlighting-menu)
- [Elements in Desktop Tests](#elements-in-desktop-tests)

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">this video tutorial for recording an end-to-end Desktop test scenario</a>.

## Recording Ready State

The recording in Test Studio desktop test is relatively slower than recording web or WPF tests. This is because of the underlaying technology and its capabilities. To help in improving the user experience Test Studio recorder indicates if an action is sent too early and it cannot be fetched correctly with a red label stating __'Not ready to record'__.

![Not ready to record](/img/automated-tests/desktop-testing/recording-specifics/fig1.png)

If you hold the mouse on an element for a while there is another gray label stating __'Ready to record'__.

![Ready to record](/img/automated-tests/desktop-testing/recording-specifics/fig2.png)

## Highlighting Menu

<a href="/features/recorder/compact-recording-toolbar#hover-over-highlighting" target="_blank">Highlighting</a> can be enabled from the Compact Recording Toolbar. The highlighting menu appears after you hold the mouse shortly over an element and allows you to add basic verification and action steps, as well as adding the hovered element into the Elements repository.

![Highlighting menu options](/img/automated-tests/desktop-testing/recording-specifics/fig3.png)

Some of the options in the menu remain grayed out until the desktop testing feature is in Beta state.

### Close the Highlighting Menu

There is an additional option in the highlighting menu for desktop applications - __Close Menu__. This is introduced as the menu remains opened if no step is added through this.

![Close Highlighting menu](/img/automated-tests/desktop-testing/recording-specifics/fig4.png)

## Elements in Desktop Tests

The elements recorded in desktop applications have their own _TechnologyType_, which is called __Desktop__.

![Elements technology type](/img/automated-tests/desktop-testing/recording-specifics/fig5.png)

Elements are added with automatically generated find expression based on their attributes in the application elements tree. If you open an element in <a href="/automated-tests/elements/find-element#options-in-element-pane-with-active-recording-session" target="_blank">_Edit mode_ in a live recording session</a> you can see the list of its attributes, which can be used in the find expression.

![Elements edit mode](/img/automated-tests/desktop-testing/recording-specifics/fig6.png)

## See Also:

* <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">Desktop Test Recording Video Tutorial</a>.
