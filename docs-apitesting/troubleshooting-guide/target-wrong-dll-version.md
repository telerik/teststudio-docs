---
title: Targeting Wrong API Framework DLL Version After Upgrade
page_title: Targeting Wrong API Framework DLL Version After Upgrade
description: "Progress® Test Studio® for APIs - Troubleshooting guide - Targeting Wrong API Framework DLL Version After Upgrade. Error 'Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=' or one of its dependencies. The system cannot find the file specified. Die Datei oder Assembly 'Telerik.ApiTesting.Framework, Version=' oder eine Abhängigkeit davon wurde nicht gefunden. Das System kann die angegebene Datei nicht finden."
position: 4
published: true
---
# Targeting Wrong API Framework DLL Version After Upgrade

## Issue

*After upgrading Test Studio to the latest available version, a coded step in the API testing project cannot be executed. All tests, which use that coded step throw error:*

```
Could not load file or assembly 'Telerik.ApiTesting.Framework, Version=XXXX.X.XX' or one of its dependencies
```

*Any tests, which are not targeting that coded step, can be executed successfully.*

## Solution

After upgrading Test Studio to a newer version, any API project which uses coded steps, will need to manually update the dll files to the current installed version. This is also applicable in the case when the <a href="https://docs.telerik.com/teststudio/features/execute-apitest/add-api-test-as-step">API project is embedded in a Web functional test project<\a>.

1. Open the API project root folder.
2. Locate the sub-folder *bin* - it contains the project dll file, which was built against the previous Test Studio version.
3. In order to force the project compilation to use the latest version of Test Studio assembly files, delete that same API project *bin* folder.
4. As a last step, compile the project.
