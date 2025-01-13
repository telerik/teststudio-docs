---
title: Transfer Files
page_title: Transfer Files
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
published: false
---
# How to Transfer Files

We can even perform complete file uploads and downloads with Telerik Testing Framework automatically handling all of the popup dialogs that appear as part of the file upload/download:

````C#
// Initiate a file upload
Find.ByTagIndex<HtmlInputFile>("input", 0).Upload(
     Path.Combine(Globals.PATH_TO_PAGES, @"..\SupportFiles\EmptyTextFile.txt"), 5000);
  
// Initiate a file download. Download will not return until the download is complete.
Find.ByTagIndex<HtmlAnchor>("a", 0).Download(false, DownloadOption.Save, saveLocation, 20000);
````
````VB
' Initiate a file upload
Find.ByTagIndex(Of HtmlInputFile)("input", 0).Upload( _
     Path.Combine(Globals.PATH_TO_PAGES, "..\SupportFiles\EmptyTextFile.txt"), 5000)
  
' Initiate a file download. Download will not return until the download is complete.
Find.ByTagIndex(Of HtmlAnchor)("a", 0).Download(False, DownloadOption.Save, saveLocation, 20000)
````