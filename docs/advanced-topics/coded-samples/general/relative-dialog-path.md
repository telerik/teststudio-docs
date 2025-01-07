---
title: Relative Dialog Path
page_title: Relative Dialog Path
description: "Use relative paths in a Test Studio test - upload/download dialog handling."
position: 1
---

# Use Relative Paths in File Upload/Downloads

*I need to upload/download a file to a path relative to my test execution folder. I don't want to use an absolute file path.*

## Solution

This can only be done in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a>. The key is to use this.ExecutionContext.DeploymentDirectory. This property identifies the folder the test is running in. You want to use it in a coded step to create an absolute path for file upload/download like this:

```C#
public void RelativePathDownloadStep()
{
    Directory.CreateDirectory(System.IO.Path.Combine(this.ExecutionContext.DeploymentDirectory, "download"));
    string fullPath = System.IO.Path.Combine(this.ExecutionContext.DeploymentDirectory, "download\\myfile.txt");
    Pages.ThinkbroadbandDownload.IconDownload5MBPngImage.Download(false, DownloadOption.Save, fullPath, 30000);
}
```
```VB
Public Sub RelativePathDownloadStep()
	Directory.CreateDirectory(System.IO.Path.Combine(Me.ExecutionContext.DeploymentDirectory, "download"))
	Dim fullPath As String = System.IO.Path.Combine(Me.ExecutionContext.DeploymentDirectory, "download\myfile.txt")
	Pages.ThinkbroadbandDownload.IconDownload5MBPngImage.Download(False, DownloadOption.Save, fullPath, 30000)
End Sub
```

You'll have to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">add an assembly reference</a> to *System.Windows.Forms.dll* and to include the following line at the top of your code file to use the given sample:

```C#
using System.IO;
```
```VB
Imports System.IO
```