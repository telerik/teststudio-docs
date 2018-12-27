---
title: Transfer Files
page_title: Transfer Files | Test Studio Dev Documentation
description: Transfer Files
position: 2
---
#How to Transfer Files#

We can even perform complete file uploads and downloads with Telerik Testing Framework automatically handling all of the popup dialogs that appear as part of the file upload/download:

#### __[C#]__

            {{region }}

    // Initiate a file upload
    Find.ByTagIndex<HtmlInputFile>("input", 0).Upload(
        Path.Combine(Globals.PATH_TO_PAGES, @"..\SupportFiles\EmptyTextFile.txt"), 5000);
    
    // Initiate a file download. Download will not return until the download is complete.
    Find.ByTagIndex<HtmlAnchor>("a", 0).Download(false, DownloadOption.Save, saveLocation, 20000);
{{endregion}}
 

#### __[C#]__

            {{region }}

    ' Initiate a file upload
    Find.ByTagIndex(Of HtmlInputFile)("input", 0).Upload( _
        Path.Combine(Globals.PATH_TO_PAGES, "..\SupportFiles\EmptyTextFile.txt"), 5000)
    
    ' Initiate a file download. Download will not return until the download is complete.
    Find.ByTagIndex(Of HtmlAnchor)("a", 0).Download(False, DownloadOption.Save, saveLocation, 20000)
    {{endregion}}


