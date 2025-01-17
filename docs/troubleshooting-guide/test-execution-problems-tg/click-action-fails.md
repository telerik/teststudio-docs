---
title: Click Action is Offset
page_title: Click is offset during test execution and causes failure
description: "The mouse clicks outside of the actual element in the page. THe clicks are misaligned. Click with simulate real user behavior fails. Enter text step fails. Enter text is offset. Offset click during execution. Desktop click fails. Simulate real click not working as expected. Click is offset from button."
position: 1
---
# Click Action is Offset

## Problem

When executing a test with real user actions, like **SimulateRealClick**, **SimulateRealTyping** or <a href="/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions" target="_blank"><strong>desktop click</strong></a>, the click action is offset. As a result the expected button is not triggered, or text is not entered in the input field, and the test fails.

![Click Offset][1]

### Cause

A couple of settings may affect the highlighitng and these are listed below:

1. __Display scale setting__ set to other than 100%.
2. Windows option to __enlarge text and apps size__ set to other than 100%.
3. Only applicable for using the browsers in the automation mode with extension - browser zoom level set to other than 100%.

## Solution

Check the three possible settings which affect the highlighting and set these to 100%. 

### Display Scale Settings 

To access the Display settings in Windows: 

1. Open Windows Start menu and type __Display Settings__. 
2. Choose the suggestion __Change the resolution of the display__. 
3. Under __Scale and Layout__ section check the value set for the first option - __Change the size of text, ..__. 
4. Ensure to set this to 100%. 

![Display scale settings][2]

### Enlarge Text and Apps Option 

The Windows options to <a href="https://support.microsoft.com/en-us/windows/make-text-and-apps-bigger-c3095a80-6edd-4779-9282-623c4d721d64" target="_blank">enlarge text and apps size</a> allows the user to choose the size of text and images in applications as part of the __Ease of Access__ settings. 

1. Press the Windows key + U to open the __Ease of Access__ settings. 
2. Under __Make text bigger__ section, drag the slider to the left to set it to 100%.

![Larger text settings][3]

### Browser Calibration Settings

Ensure <a href="/features/project-settings/browsers" target="_blank">the browser is calibrated</a>. 


[1]: /img/troubleshooting-guide/test-execution-problems-tg/click-action-fails/fig1.png
[2]: /img/troubleshooting-guide/recording-problems-tg/highlighting-misaligned/fig2.png
[3]: /img/troubleshooting-guide/recording-problems-tg/highlighting-misaligned/fig3.png


