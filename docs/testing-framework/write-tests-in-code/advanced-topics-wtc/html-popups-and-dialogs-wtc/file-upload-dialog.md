---
title: FileUpload Dialog
page_title: FileUpload Dialog
description: "Handle a upload file dialog in a coded step in Test Studio. Coded test to handle upload file dialogs in Test Studio. Test Studio Testing Framework Upload File Dialog handling."
position: 6
---
# FileUpload Dialog

With FileUpload, you need to pass in the full path to the file to upload and how the dialog should be handled. The options for FileUpload are: DialogButton.OPEN, DialogButton.CANCEL or DialogButton.CLOSE.

````C#
// Add a FileUpload dialog to be monitored.
Manager.DialogMonitor.AddDialog(new FileUploadDialog(ActiveBrowser, @"C:\EmptyTextFile.txt", DialogButton.OPEN));
  
// Given that there were no dialog attribute set, the manager will not start the monitoring.
// You need to invoke the monitoring
Manager.DialogMonitor.Start();
  
// Cause the upload Dialog to pop-up
// With Firefox, it is not allowed to pop the dialog using script due to security restrictions.
  
//Click a button which triggeres the dialog
Pages.YourSite.YourButton.Click();
  
// Dialog should be automatically handled
````
````VB
' Add a FileUpload dialog to be monitored.
Manager.DialogMonitor.AddDialog(New FileUploadDialog(ActiveBrowser, Path.Combine(Globals.PATH_TO_PAGES, "..\SupportFiles\EmptyTextFile.txt"), DialogButton.OPEN))
  
' Given that there were not dialog attribute set, the manager will not start the monitoring.
' You need to invoke the monitoring
Manager.DialogMonitor.Start()
  
' Cause the upload Dialog to pop-up
Pages.YourSite.YourButton.Click()
````

## Multiple Files Upload

There are scenarios where multiple files needs to be uploaded. Below you could find a sample code how to obtain that with the Testing Framework. The code will loop through a set of files and will upload each after the previous. The sample is built against a <a href="https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_fileupload_multiple" target="_blank">public accessible webpage</a> and to give a try to that example you have to first navigate to that page. 

````C#
// place small pictures with names file1.png and file2.png in c:\temp folder to have the sample working without modification
string path = @"C:\temp\" ;
string[] fileNames = new string[] { "file1.png", "file2.png" } ;

// locate the frame on page
FrameInfo frInf = new FrameInfo("iframeResult", "", "", 0);
Browser frame = ActiveBrowser.Frames[frInf];
    
// locate file browse button
HtmlInputFile uploadBtn = frame.Find.ById<HtmlInputFile>("myFile");
// locate Submit button
HtmlInputSubmit submitBtn = frame.Find.ByAttributes<HtmlInputSubmit>("type=submit");

for (int i = 0; i < fileNames.Length; i++ )
{
    // add a FileUpload dialog to be monitored
    FileUploadDialog uploadDialog = new FileUploadDialog(ActiveBrowser, path + fileNames[i] , DialogButton.OPEN);
    Manager.DialogMonitor.AddDialog(uploadDialog);

    // start the Dialog Monitoring
    Manager.DialogMonitor.Start();

    // click on the button which triggeres the dialog
    uploadBtn.MouseClick();

    // wait on handling the dialog for 10 seconds
    uploadDialog.WaitUntilHandled(10000);

    // The dialog should be automatically handled

    // Remove the current dialog from the DialogMonitoring collection, once it is handled
    Manager.DialogMonitor.RemoveDialog(uploadDialog);

    // Click 'Submit' to upload the file
    submitBtn.MouseClick();

    // execution delay to check on the uploaded content - 2 seconds
    System.Threading.Thread.Sleep(2000);

    // Refresh the page to be ready to upload next file
    ActiveBrowser.Refresh();
}

````

> **Note** To compile the above code include the following using:
>
> using ArtOfTest.WebAii.Win32.Dialogs;

**See also:** <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/html-control-suite-wtc/transfer-files" target="_blank">How to Transfer Files</a>
