---
title: Window Partial Match
page_title: How to Indicate a Partial Match for WPF Window Name
description: "Learn how to handle dynamic WPF window titles in Test Studio by using partial match techniques. This article explains how to edit the Caption property for reliable element identification during automated test execution."
position: 1

---
# How to Indicate a Partial Match for WPF Window Name

## PROBLEM

I have a dynamic window title in my application. Elements in the window cannot be located during execution because the title differs from when it was recorded.

## SOLUTION

Edit the **Caption** property for the Window node in the Elements Explorer. Use a leading tilde (~) character to indicate a partial match and remove the dynamic portion.

<table id="no-table">
<tr>
<td>![fig1][1]<br>![fig2][2]<br>**Original Window Caption**</td>
<td>![fig3][3]<br>![fig4][4]<br>**Edited for Partial Match**</td>
</tr>
<table>

[1]: /img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig4.png