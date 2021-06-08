---
title: Highlighting an Element
page_title: Highlighting an Element While Recording
description: "The Compact Toolbar in Test Studio allows you to highlight different elements on a page and to use various functions in the highlighting menu."
position: 2
---
# Highlighting Elements in Recording Mode

The __Highlighting menu__ provides a set of options that enable you to interact with the targeted element.

This article explains how to use the Highlighting feature in the Test Studio recorder.

1. [How to Enable or Disable the Highlighting](#enable-or-disable-highlighting-of-elements)
1. [Quick Steps in Highlighting Menu](#quick-steps)
1. [Mouse Actions in Highlighting Menu](#mouse-actions)
1. [Scroll Actions in Highlighting Menu](#scroll-actions)
1. [_Add to Elements_ Option in Highlighting Menu](#add-to-elements)
1. [_Locate in DOM_ Option in Highlighting Menu](#locate-in-dom)
1. [_Build Step_ Option in Highlighting Menu](#build-step)

## Enable or Disable Highlighting of Elements

When a recording session is active, you can enable or disable the Highlighting from the <a href="/features/recorder/compact-recording-toolbar" target="_blank">**Compact Recording Toolbar**</a>.

![Enable\disable highlighting](/img/automated-tests/recording/highlighting/fig1.png)

> **Note**
> <br>
> <br>
> You can enable or disable the Highlighting feature even when the recording is paused.

When Highlighting is enabled and the mouse pointer pauses over an element in the recording surface of the tested application, you will see the __Elements menu__. This menu provides quick access to functions related to the tested application.

![Elements Menu](/img/automated-tests/recording/highlighting/fig2.png)

> **Tip**
> <br>
> <br>
> Use the `Pause` or `Break` key on your keyboard to toggle the Highlighting feature on or off.

## Options in the Highlighting Menu

The __Elements Menu__ provides access to various actions and functions beyond the straightforward _click_ or _type_ actions. These are divided into sub-menus that are described in the following document sections.

### Quick Steps

The __Quick Steps__ sub-menu provides a list of tasks that can be performed against the highlighted element - these are context sensitive and will be different depending on the target element. A few options are listed: to add a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">__quick verification__</a>, a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">__wait step__</a> or <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">__to extract any of the element's attributes__</a> based on its specifics.

![Quick Steps Sub-menu](/img/automated-tests/recording/highlighting/fig4.png)

### Mouse Actions

The __Mouse Actions__ sub-menu provides quick access to different types of click steps like double-click, right-click, mouse key up or down, hover action, etc. The mouse click steps are __recorded with specific coordinates__ relevant to the target element where the click will be sent. The default setting is the element's absolute center, but you can choose to <a href="/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions#specific-location" target="_blank">change this in the Advanced Recording Tools actions section</a>.

![Mouse Actions Sub-menu](/img/automated-tests/recording/highlighting/fig5.png)

> **Tip**
> <br>
> <br>
> The __Drag and Drop action__ requires the selection of the element to drag and the element to drop it to. Therefore, this can only be <a href="/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop" target="_blank">added through the Advanced Recording Tools</a>.

### Scroll Actions

The __Scroll Actions__ sub-menu enables you to scroll the page and change its visible area. The available options allow you to choose an application element and scroll it to the top, bottom or center of the page.

![Scroll Actions Sub-menu](/img/automated-tests/recording/highlighting/fig6.png)

> **Note**
> <br>
> <br>
> You can access the __Quick Steps__, __Mouse Actions__ and __Scroll Actions__ options in the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Advanced Recording Tools</a>, where you can also find additional step types that you can add against a selected element.

### Add to Elements

The **Add to Elements** option allows you to add the highlighted element to the selected test in the project as an _external reference_ - an element that isn't related to any step from the test but is still listed can be referred from a coded step, for example.

![Add to Elements][5]

### Locate in DOM

**Locate in DOM** is an option that directly opens the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer in the __Advanced Recording Tools__</a> and selects the highlighted element in the DOM structure of the page. You can further explore the surrounding elements of the selected one, or use the options for building a step using this element.

![Locate in DOM][6]

### Build Step

**Build Step...** is similar to the __Locate In DOM__ option - it selects the highlighted element in the DOM tree and directly switches to the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Element Steps</a> tab in the __Advanced Recording Tools__.

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
