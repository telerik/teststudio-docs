---
title: Changing Cached Credentials for TFVC Source Control in Telerik Test Studio
description: Learn how to clear cached credentials for TFVC type source control repository associated with a Telerik Test Studio project.
type: how-to
page_title: Clearing TFVC Cached Credentials in Test Studio
meta_title: Clearing TFVC Cached Credentials in Test Studio
slug: clearing-tfvc-cached-credentials-test-studio
tags: telerik test studio, tfvc, source control, credentials, perusersettings.json
res_type: kb
ticketid: 1503880
---

## Description

I need to __update cached credentials for a TFVC source control repository__ associated with my Telerik Test Studio project. However, Test Studio doesn't prompt me for updated credentials even after attempting various steps like workspace removal, Credential Manager cleanup, and project disconnection.

This knowledge base article also answers the following questions:
- How to reset TFVC credentials in Telerik Test Studio?
- How to enable credential prompts in Test Studio after changes?
- Where are TFVC credentials stored for Test Studio projects?

## Solution

To refresh cached credentials for a TFVC repository, follow these steps:

1. Locate the Test Studio internal settings file in the user folder: `C:\Users\<YourUsername>\AppData\Roaming\ArtOfTest`.
2. Open the `PerUserSettings.json` file using a text editor like Notepad++.
3. Find the setting `"TfsSkipAuth"` in the file.
4. Change the value of `"TfsSkipAuth"` from `true` to `false`.
5. Save the changes to the file.
6. Delete the `WebUITestStudio.json` file in the same directory.
7. Start Telerik Test Studio.
8. Attempt to connect to the TFVC repository. Test Studio will prompt for credentials.


  
