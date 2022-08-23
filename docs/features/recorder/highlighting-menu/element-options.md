---
title: Element Options
page_title: Element Options in the Hihglighting Menu
description: "Test Studio Highlighting menu in recording mode provides quick selection of the highlighted element in the DOM or quick addition to the Elements Repository."
position: 3
---
# Element Options in the Hihglighting Menu

The __Highlighting menu__ provides a powerful set of options related to the targeted element. It brings additional options to interact with an element in the terms of test recording, apart from clicking or entering text.

You can read further about the Element options:

* [Add to Elements](#add-to-elements)
* [Locate in DOM](#locate-in-dom)
* [Build Step](#build-step)

![Element Options in Highlighting menu][1]

> **Tip**
> <br>
> <br>
> Check out this <a href="https://www.youtube.com/watch?v=dIiXjwsPUtA&list=PLvmaC-XMqeBa7evdakaPkd_kctAJRm85h&index=4">neat video tutorial</a> which will help in analyzing the elements in the tested application.

## Add to Elements

**Add to Elements** option allows you to add the highlighted element to the <a href="/automated-tests/elements/overview" target="_blank">Elements Explorer</a>. It is referenced in the selected test in project as an _'external reference'_ - that means the element is not related to a particular step from the test, but is still listed in it and can be referred from a coded step, for example.

![Add to Elements][5]

## Locate in DOM

**Locate in DOM** is the option, which directly opens the __Advanced Recording Tools__ window with its <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer tab</a> active.  The highlighted element is selected in the DOM structure of the application. That way you can  explore the surrounding elements. It can be useful when you need to change the find expression of an element and need to get familiar with its attributes and parent elements.

![Locate in DOM][6]

## Build Step

**Build Step...** is the option, which selects the highlighted element in the DOM tree and switches to the <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">Element Steps tab</a> in the __Advanced Recording Tools__. It is useful when you need to build an advanced step against the element such as <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">image verification</a> or a mouse click step which clicks on specific point of the target element.

![Build Step][7]

[1]: /img/features/recorder/highlighting-menu/fig1.png
[5]: /img/features/recorder/compact-recording-toolbar/fig5.png
[6]: /img/features/recorder/compact-recording-toolbar/fig6.png
[7]: /img/features/recorder/compact-recording-toolbar/fig7.png
[8]: /img/features/recorder/compact-recording-toolbar/fig8.png
[9]: /img/features/recorder/compact-recording-toolbar/fig9.png
[10]: /img/features/recorder/compact-recording-toolbar/fig10.png
[11]: /img/features/recorder/compact-recording-toolbar/fig11.png
[12]: /img/features/recorder/compact-recording-toolbar/fig12.png
[13]: /img/features/recorder/compact-recording-toolbar/fig13.png
