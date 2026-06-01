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

<table id="no-table" style="border:none;">
<tr style="text-align: center; background-color: transparent; border:none;">
<td>

<img src="/img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig1.png" alt="fig1" /><br><img src="/img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig2.png" alt="fig2" /><br>**Original Window Caption**</td>
<td>

<img src="/img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig3.png" alt="fig3" /><br><img src="/img/troubleshooting-guide/test-execution-problems-tg/wpf-tg/window-partial-match/fig4.png" alt="fig4" /><br>**Edited for Partial Match**</td>
</tr>
</table>

