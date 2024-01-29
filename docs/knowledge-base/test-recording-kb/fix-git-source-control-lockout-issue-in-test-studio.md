---
title: Troubleshooting Git Source Control Lockout Issue
description: Learn how to troubleshoot the issue of being locked out of source control when pushing commits in Test Studio.
type: troubleshooting
page_title: Fix Git Source Control Lockout Issue in Test Studio
slug: fix-git-source-control-lockout-issue-in-test-studio
tags: git, source control, lockout, push commits, troubleshooting
res_type: kb
---

## Description
When pushing commits to Git source control in Test Studio, you may encounter an issue where you are automatically locked out and the changes are not pushed.

## Solution
To fix the Git source control lockout issue, follow these steps:

1. Open the local copy of the project stored on your computer.
2. Disconnect the project from Git by removing the binding in the context menu. Exit Test Studio.
3. Locate the `Settings.aiis` file in the local project root folder and open it with Notepad++.
4. Search for the `ProjectGuid` node and note its value.
5. Browse to the folder `C:\Users\[YourUsername]\AppData\Roaming\ArtOfTest\` and find the `WebUITestStudio.json` file. Open it with Notepad++.
6. Search for the project GUID you noted in the previous step.
7. Delete the corresponding section of the file and save it.
8. Close both files in Notepad++.
9. Start Test Studio and open the previously disconnected project.
10. Use the "Connect to Git" option and enter the correct credentials (using a personal access token instead of a password).
11. Test pushing and pulling changes to ensure the issue is resolved.

If you continue to experience any issues or have further questions, please reach out to us for assistance.
