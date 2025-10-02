---
title: Window Partial Match
page_title: How to Indicate a Partial Match for WPF Window Name
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
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

[1]: /img/troubleshooting-guide/test-execution-problems-tg/silverlight-wpf-tg/window-partial-match/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/silverlight-wpf-tg/window-partial-match/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/silverlight-wpf-tg/window-partial-match/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/silverlight-wpf-tg/window-partial-match/fig4.png