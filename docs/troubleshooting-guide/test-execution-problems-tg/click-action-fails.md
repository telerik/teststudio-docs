---
title: Click Action Fails
page_title: Click is offset during test execution and causes failure
description: "Real click fails. Enter text step fails. Enter text is offset. Offset click during execution. Desktop click fails. Simulate real click not working as expected. Click is offset from button."
position: 1
---
# Click Action is Offset

##Problem

When executing a test with real user actions, like **SimulateRealClick**, **SimulateRealTyping** or <a href="/recorder/advanced-recording-tools/element-steps/actions/mouse-actions" target="_blank"><strong>desktop click</strong></a>, the click action is offset. As a result the expected button is not triggered, or text is not entered, and the test fails. 

![Click Offset][1]

##Solution

1. <a href="/features/project-settings/browsers" target="_blank">Calibrate</a> your browser. Test Studio tests are meant to always be run with the browser zoom level at 100%.

2. Set the monitor's **DPI** setting at **Smaller** or **100%** as well.

##Windows 10

1. Go to Control Panel -> Appearance and Personalization -> Display

2. Click on **set a custom scaling level** (refer to the highlighted)

3. Select 100% from the dropdown  

![win 10][4]

##Windows 8

1. Go to Control Panel -> Appearance and Personalization -> Display

2. Check **Let me choose one scaling level for all my displays** check box

3. Select **Smaller - 100%** and click Apply

![win 8][2]


##Windows 7

1. Go to Control Panel -> Appearance and Personalization -> Display

2. Select **Smaller - 100%** and click Apply

![win 7][3]



[1]: /img/troubleshooting-guide/test-execution-problems-tg/click-action-fails/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/click-action-fails/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/click-action-fails/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/click-action-fails/fig4.png
