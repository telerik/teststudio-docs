---
title: No File Path for Upload Step in IE 10
page_title: No File Path for Upload Step in IE 10
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# No file path for IE 10 upload dialog

## PROBLEM

In Internet Explorer 10, recording against a file upload dialog may record a dialog handler step with no file path.

![Steps][1]

## SOLUTION

In Windows 8, the default folder settings hide known file extensions, which prevents Test Studio file path recording. To fix this behavior, disable the 'Hide extensions for known file types' setting in the Folder Options View tab for the origin folder.

![Folder Options][2]

[1]: /img/troubleshooting-guide/recording-problems-tg/no-file-path-ie10/fig1.png
[2]: /img/troubleshooting-guide/recording-problems-tg/no-file-path-ie10/fig2.png