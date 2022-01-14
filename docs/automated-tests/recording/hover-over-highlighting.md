---
title: Highlighting an Element
page_title: Highlighting an Element While Recording
description: "The Compact Toolbar allows you to highlight the elements on page. Highlight elements in WPF app. Use the options from Elements menu for the specific element. How to add an element in project without recording a step for it. How to check where in the DOM is certain element on page"
position: 2
---
# Highlighting Elements in Recording Mode

The __Highlighting menu__ is a powerful set of options related to the targeted element. It brings additional options to interact with an element in the terms of test recording, apart from clicking or entering text.

In this article you will find useful details and hints about the highlighting feature in Test Studio recorder and how to get most benefits of this.

1. [How to Enable or Disable the Highlighting](#enable-or-disable-highlighting-of-elements)
1. [Quick Steps in Highlighting Menu](#quick-steps)
1. [Mouse Actions in Highlighting Menu](#mouse-actions)
1. [Scroll Actions in Highlighting Menu](#scroll-actions)
1. [_Add to Elements_ Option in Highlighting Menu](#add-to-elements)
1. [_Locate in DOM_ Option in Highlighting Menu](#locate-in-dom)
1. [_Build Step_ Option in Highlighting Menu](#build-step)

> **Tip**
> <br>
> <br>
> Check out this <a href="https://www.youtube.com/watch?v=dIiXjwsPUtA&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=4">neat video tutorial</a> which will help in analyzing the elements in the tested application.

## Enable or Disable Highlighting of Elements

Once in an active recording session you can enable or disable the _highlighting_ from the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a>.

![Enable\disable highlighting](/img/automated-tests/recording/highlighting/fig1.png)

> **Note**
> <br>
> <br>
> The highlighting feature __can be enabled (or disabled) even when the recording is paused__.

When enabled and the mouse pointer pauses over an element in the recording surface of the tested application, you will see the __Elements menu__ with multiple options. This rich menu makes it easy to work with the recording surface and its elements. It provides quick access to relevant functions right in the application you are testing.

![Elements Menu](/img/automated-tests/recording/highlighting/fig2.png)

> **Tip**
> <br>
> <br>
> Use the *Pause/Break* key on your keyboard to toggle on or off the Highlighting feature.

## __Options in the Highlighting Menu__

The __Elements Menu__ provides access to various actions and functions apart from the straightforward _click_ or _type_ actions. These are divided in few sections to speed up their usage. Read below what options there are in the different sub-menus.

## Quick Steps

__Quick Steps__ sub-menu provides a list of tasks, which can be performed against the highlighted element - these are context sensitive and will be different depending on the target element. There are few options listed to add a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">__quick verification__</a>, a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">__wait step__</a> or <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">__to extract any of the element's attributes__</a>, based on its specifics.

![Quick Steps Sub-menu](/img/automated-tests/recording/highlighting/fig4.png)

## Mouse Actions

__Mouse Actions__ sub-menu provides quick access to different type of click steps like double-click, right mouse click, mouse key up or down, mouse hover over action, etc. The mouse click steps are getting __recorded with specific coordinates__ relevant to the target element, where the click will be sent. The default set is the element's absolute center, but you can choose to <a href="/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions#specific-location" target="_blank">change this in the Advanced Recording Tools actions section</a>.

![Mouse Actions Sub-menu](/img/automated-tests/recording/highlighting/fig5.png)

> **Tip**
> <br>
> <br>
> The __Drag and Drop action__ requires the selection of the element to drag and the element to drop it to. Therefore, this can only be <a href="/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop" target="_blank">added through the Advanced Recording Tools</a>.

## Scroll Actions

In certain occasions you may need to scroll the page and change the visible part of it. The __Scroll Actions__ sub-menu gives the options to choose an element on application screen and scroll it to the top, bottom or center of the page.

![Scroll Actions Sub-menu](/img/automated-tests/recording/highlighting/fig6.png)

> **Note**
> <br>
> <br>
> The __Quick Steps__, __Mouse Actions__ and __Scroll Actions__ options can be all accessed in the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Advanced Recording Tools</a>. There you can find also additional type of steps to add against a selected element.

## Add to Elements

**Add to Elements** option allows you to add the highlighted element to the selected test in project as an _'external reference'_ - that means the element is not related to any step from the test, but is still listed in it and can be referred from a coded step, for example.

![Add to Elements][5]

## Locate in DOM

**Locate in DOM** is an option, which directly opens the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer in the __Advanced Recording Tools__</a> and selects the highlighted element in the DOM structure of the page. You can further explore the surrounding elements of the selected one, or use the options for building a step using this element.

![Locate in DOM][6]

## Build Step

**Build Step...** is an option very similar to the __Locate In DOM__ one - it selects the highlighted element in the DOM tree and directly switches to the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Element Steps</a> tab in the __Advanced Recording Tools__.

![Build Step][7]

There are additional actions and verifications you can add against the selected element. For example, you can add mouse actions and <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">advanced verification steps</a> for attribute, image or text from image.

[1]: /img/features/recorder/compact-recording-toolbar/anim1.gif
[2]: /img/features/recorder/compact-recording-toolbar/fig2.png
[3]: /img/features/recorder/compact-recording-toolbar/fig3.png
[4]: /img/features/recorder/compact-recording-toolbar/fig4.png
[5]: /img/features/recorder/compact-recording-toolbar/fig5.png
[6]: /img/features/recorder/compact-recording-toolbar/fig6.png
[7]: /img/features/recorder/compact-recording-toolbar/fig7.png
[8]: /img/features/recorder/compact-recording-toolbar/fig8.png
[9]: /img/features/recorder/compact-recording-toolbar/fig9.png
[10]: /img/features/recorder/compact-recording-toolbar/fig10.png
[11]: /img/features/recorder/compact-recording-toolbar/fig11.png
[12]: /img/features/recorder/compact-recording-toolbar/fig12.png
[13]: /img/features/recorder/compact-recording-toolbar/fig13.png
