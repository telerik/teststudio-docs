---
title: Special Characters
page_title: Special Characters
description: "How Test Studio displays special characters in the DOM explorer. "
position: 1
---
# Special Characters

Some browsers return escaped text while others return unescaped text. Below is an example of HTML code, how it displays in Internet Explorer, and how it renders in the DOM Explorer. 

![Special Char][1]

Test Studio uses an HTML-based parser when reading the content of elements. It detects special characters and replaces them with their <a href="http://htmlhelp.com/reference/html40/entities/special.html" target="_blank">respective HTML encoding</a>. Test Studio extracts the uninterpreted string from the HTML page. What you see in the browser is an interpretation of the raw HTML code rendered to the page.

[1]: /img/troubleshooting-guide/browser-inconsistencies-tg/special-characters/fig1.png


