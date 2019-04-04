---
title: Convert .trx to HTML
page_title: Convert .trx to HTML
description: Convert .trx test results to HTML format
position: 1
---
#Convert .trx to HTML#

*I'm executing Testing Framework-powered tests with Visual Studio's MSTest runner. The results are outputted to trx result files. I would like to convert these files (which are XML-based) into HTML for easier viewing.*

##Solution##

This is doable with a custom solution. There's a number of sources on the Internet that describe how to implement this. However, we recommend that you use an CMD app that offers this functionality out of the box: **trx2html**. Download it <a href="http://trx2html.codeplex.com/" target="_blank">here</a>.
 
The application is very easy to use and will allow you to instantly convert your trx results to an HTML page. You can implement a scripted solution by using a <a href="http://en.wikipedia.org/wiki/Batch_file" target="_blank">batch file</a> to trigger the conversion.

![HTML format][1]

**Note:** This application was developed by a Microsoft employee and <a href="https://social.msdn.microsoft.com/profile/rido/" target="_blank">blogger</a> who is not affiliated with Telerik. Telerik has no rights on this application and is not involved in its development.

[1]: /img/knowledge-base/visual-studio-kb/convert-trx-to-html/fig1.png

