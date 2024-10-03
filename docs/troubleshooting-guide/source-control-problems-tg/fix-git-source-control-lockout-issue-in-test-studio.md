---
title: Troubleshooting Git Source Control Lockout Issue
description: Learn how to troubleshoot the issue of being locked out of source control when pushing commits in Test Studio. Learn how to change the Git credentials used in Test Studio project. Refresh Git credentials used in Test Studio project. Update Git passsword in Test Studio project. 
type: troubleshooting
page_title: Fix Git Source Control Unable to Push in Test Studio
slug: fix-git-source-control-lockout-issue-in-test-studio
tags: git, source control, lockout, push commits, troubleshooting
res_type: kb
---

## Description
When pushing commits to Git source control in Test Studio, you get to a state where you are automatically locked out and the changes are not pushed.

## Solution
To fix the Git source control lockout issue, follow these steps:

1. Open the local copy of the project stored on your computer.
2. <a href="/automated-tests/source-control/git/supported-git-commands#description-of-supported-commands" target="_blank">Disconnect the project from Git</a> by removing the binding in the context menu. Exit Test Studio.

    ![Remove Git Binding from project](/img/features/source-control/git/connect-to-git/fig4_removeSC.png)

3. Locate the `Settings.aiis` file in the local project root folder and open it with Notepad++.
4. Search for the `ProjectGuid` node and note its value.

    ![Project guid value from settings.aiis file](/img/troubleshooting-guide/source-control-problems-tg/change-git-credentials/project-settings-guid-value.png)

5. Browse to the folder `C:\Users\<YourUsername>\AppData\Roaming\ArtOfTest\` and find the `WebUITestStudio.json` file. Open it with Notepad++.
6. Search for the project GUID you noted in the previous step.
7. Delete the corresponding section of the file and save it - see the marked section in the image as example.

    ![Project guid section in webuiteststudio.json](/img/troubleshooting-guide/source-control-problems-tg/change-git-credentials/webui-json-git-credentials.png)

8. Close both files in Notepad++.
9. Start Test Studio and open the previously disconnected project.
10. Use <a href="/automated-tests/source-control/git/connect-to-git#connect-to-remote-repository" target="_blank">the "Connect to Git" option</a> and enter the correct credentials (__using a personal access token__ instead of a password).
11. Test pushing and pulling changes to ensure the issue is resolved.


