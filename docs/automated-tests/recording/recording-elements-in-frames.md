---
title: How to Handle Application with HTML IFrames 
page_title: How to Handle Application with HTML Frames
description: "Test Studio test Recording in application with frames. How Test Studio handles iframes in web page? Can I record elements listed under iframe with Test Studio? How frames are recorded in Test Studio? How frames are recognized in Test Studio? Can Test Studio detect dynamic frames and automate these? Test Studio dynamic frames handling."
position: 4
---
# How to Handle Application with HTML IFrames

Test Studio has built-in mechanism to recognize iFrames in web applications' DOM tree and records the elements in these automatically. Depending on the page structure and implementation of frames, you may even miss the fact there are frames in the application and related to the elements added in the test project.

If you need to know more about HTML frames structure, this article describes how elements in iFrames are recorded and represented in the Test Studio project.

## How Frames are Listed in the DOM Explorer

The target page of the below example is a <a href="https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_iframe" target="_blank">demo W3School page for iframes</a>. The test sceanrio verifies the displayed text on few elements on the page (highlighted on the image below).

![Frames Demo App](/img/automated-tests/recording/recording-frames/fig1.png)

The W3School demo pages always display the result of a sample in a frame. For this particular example, there is one more frame nested in the _Results_ frame. In Test Studio <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a> the nested frames are represented as in the actual DOM tree of the page.

![DOM Explorer of Frames Demo App](/img/automated-tests/recording/recording-frames/fig2.png)

If there are any frames on the page, these will be listed in a dropdown in the Test Studio recorder DOM Explorer - this is the parent node filter dropdown. It allows you to choose which node from the DOM tree to display in the Explorer and work with it to <a href="/features/recorder/advanced-recording-tools/element-steps/steps-overview" target="_blank">add steps</a> against its elements.

![DOM Explorer parent node filter](/img/automated-tests/recording/recording-frames/fig3.png)

## Recording Actions against IFrames

In the general case, there is nothing specific in the recording experience against the elements of a frame - you can directly perform the actions against the page to add steps in the test, or choose an option from the <a href="/automated-tests/recording/hover-over-highlighting" target="_blank">Highlighting menu</a>.

The steps recorded against elements in frames look the same way as any other step. What makes the difference is how the target element is listed in the Elements Explorer - there is an additional <a href="/automated-tests/elements/frames" target="_blank">node, which represents the frame element</a> for Test Studio.

![Steps Recorded in Test](/img/automated-tests/recording/recording-frames/fig0.png)

> **Tip**
> <br>
> <br>
> Find out more for the frame nodes in the Elements Explorer in <a href="/automated-tests/elements/frames" target="_blank">this dedicated article</a>.

## Disable Auto-Refresh for the DOM Explorer

If the application under test has dynamically changing content, for example a countdown watch, this causes the Element Tree in the DOM Explorer to constantly refresh. In such cases you can use the _Freeze/Unfreeze_ button to stop the auto-refresh action, and the _Refresh_ button to fetch the current state of DOM tree.

![Freeze/Unfreeze/Refresh DOM tree state](/img/automated-tests/recording/recording-frames/fig4.png)
