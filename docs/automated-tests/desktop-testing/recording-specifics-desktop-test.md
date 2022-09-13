---
title: Recording Desktop Tests
page_title: Recording Desktop Test
description: "Testing a desktop app with Test Studio. Specifics in recording desktop application scenarios in Test Studio. Record an automated scenario for desktop app in Test Studio. "
position: 1
---
# Recording Specifics for Desktop Tests in Test Studio

Test Studio recording feature supports various desktop applications. Once a desktop test is configured for specific application you can start recording the automation scenarios.

This article guides you through the specifics of recording steps in a desktop test.

- [Ready State for Desktop Recording](#recording-ready-state)
- [Highlighting Menu](#highlighting-menu-in-desktop-recording)
- [Advanced Recording Tools](#advanced-recording-tools-in-desktop-recording)
- [Elements in Desktop Tests](#elements-in-desktop-tests)


## Recording Ready State

The recording of desktop tests can sometimes be relatively slower than recording web or WPF tests. To make sure that all actions are recorded properly and help you build robust tests Test Studio's recorder encompass a mechanism for element state detection. When an action is sent too early before the element is ready for automation, the recorder indicates this with a red label stating __'Not ready to record'__.

![Not ready to record](/img/automated-tests/desktop-testing/recording-specifics/fig1.png)

If you hold the mouse on an element for a while there is another gray label stating __'Ready to record'__.

![Ready to record](/img/automated-tests/desktop-testing/recording-specifics/fig2.png)

> **Tip**
> <br>
> <br>
> Check <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">this video tutorial for recording an end-to-end Desktop test scenario</a>.

## Highlighting Menu in Desktop Recording

Highlighting is enabled from the <a href="/features/recorder/compact-recording-toolbar#enable-hover-over-highlighting" target="_blank">Compact Recording Toolbar</a>. The <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">highlighting menu</a> appears after you hold the mouse shortly over an element and allows you to add basic <a href="/features/recorder/highlighting-menu/quick-steps/quick-verification" target="_blank">verification</a> and <a href="/features/recorder/highlighting-menu/mouse-actions" target="_blank">action steps</a>.

![Highlighting menu options](/img/automated-tests/desktop-testing/recording-specifics/fig3.png)

The highlighting menu lists <a href="/features/recorder/highlighting-menu/element-options" target="_blank">additional options related to the highlighted element</a.> 

- To add the target element to the Elements Explorer;
- Select the target element in the DOM Explorer in the Advanced Recording tools; 
- Select the target element in the DOM Explorer and expose the options for adding steps for it. 

![Highlighting menu options](/img/automated-tests/desktop-testing/recording-specifics/fig3a.png)

The highlighting menu in desktop applications may remain opened over part of the application you want to interact with. In such cases you can use the __Close Menu__ option to hide it. 

![Close Highlighting menu](/img/automated-tests/desktop-testing/recording-specifics/fig4.png)

## Advanced Recording Tools in Desktop Recording

The __Advanced Recording Tools__ window provides all its functionalities in a recording session for desktop application - the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a> tab, the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Elements Steps</a> and <a href="/features/recorder/advanced-recording-tools/common-steps" target="_blank">Common Steps</a> tabs. 

![Advanced Recording Tools in Desktop app](/img/automated-tests/desktop-testing/recording-specifics/fig40.png)

## Elements in Desktop Tests

The elements recorded in desktop applications have their own _TechnologyType_, which is called __Desktop__.

![Elements technology type](/img/automated-tests/desktop-testing/recording-specifics/fig5.png)

Test Studio automatically generates find expressions for the elements from the tested desktop application. It uses the <a href="/features/project-settings/find-logic#find-logic-for-desktop-elements" target="_blank">__Smart Find Logic setting for desktop elements__</a> to choose which attribute to use in generating the elements expressions. 

> __Tip__
><br>
><br>
> The default set attribute for generating find expressions is 'ControlTypeName'. Depending on the tested desktop app specifics, you can choose to create elements using xPath or ClassName by <a href="/features/project-settings/find-logic#find-logic-for-desktop-elements" target="_blank">__changing the Smart Find Logic settings on project level__</a>.

Open an element in <a href="/automated-tests/elements/find-element#options-in-element-pane-with-active-recording-session" target="_blank">_Edit mode_ in a live recording session</a> to see the list of its attributes, which can be used in the find expression.

![Elements edit mode](/img/automated-tests/desktop-testing/recording-specifics/fig6.png)

> __Tip__
><br>
><br>
> You can maintain the desktop elements also without active recording session although there will be no list of element properties. All <a href="/features/custom-steps/overview" target="_blank">options for adding steps offline through the __Step Builder__</a> are applicable. 

## See Also:

* <a href="https://www.telerik.com/videos/teststudio/desktop-testing-video-tutorial" target="_blank">Desktop Test Recording Video Tutorial</a>.
