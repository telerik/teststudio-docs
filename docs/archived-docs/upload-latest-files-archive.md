---
title: Upload To Storage
page_title: Upload Latest Project Files
description: You have recurring test list scheduled and you need to make some change in the test list such as editing a particular test case, add or remove tests etc. You can force uploading the changes to the database
position: 7
---
# Upload Latest Project Files to Storage Database

## Automatic Upload of Recent Changes

If you continue working within a project in which there are upcoming scheduled test lists and you attempt to save these, you will get a <a href="/features/scheduling-test-runs/schedule-execution#automatically-upload-changed-project-files-to-storage" target="_blank">notification for automatic upload of the changes</a>.

Once you choose an option and select to not be prompted in the future, the selected option will be applied by each next *Save All* action performed in the project. However, you may need to change your initial selection and here are the steps to follow to get prompted with that message again:

1. Open the project's root folder and open the *Settings.aiis* file with a text editor (Notepad++ for example). 
2. Find the Project ID value and note it somewhere.
3. Go to *C:\Users\\\<yourUserName>\AppData\Roaming\ArtOfTest* folder and locate a file named *PerUserSettings.json*.
4. Open that file with a text editor again and locate the Project ID under "SkipUploadScheduledJobToStoragePromptPerProject" setting. Delete the project's id and save the file.

Then when you start the project again, make any change and select Save All, the dialog will prompt you again and you could choose the desired option to automatically update the files. That way all changes will be reflected in the database whenever you *Save All*.

[1]: /img/knowledge-base/scheduling-kb/upload-latest-files/fig1.png