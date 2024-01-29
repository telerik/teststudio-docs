---
title: Resolving Error CS0246 in Telerik Test Studio
description: Learn how to resolve the CS0246 compialtion error in Telerik Test Studio when running a batch remotely or locally.
type: troubleshooting
page_title: Troubleshooting Compile Error CS0246 in Telerik Test Studio
slug: troubleshooting-error-cs0246-telerik-test-studio
tags: telerik-test-studio, error-cs0246, troubleshooting
res_type: kb
---
## Description
I encounter the CS0246 error when attempting to run a batch remotely or locally in Telerik Test Studio. The error persists even when I try to run a single test using the Execute button.

## Solution
To resolve the CS0246 error, follow these steps:

1. Open the project in Telerik Test Studio.
2. Compile the project by selecting the "Compile All" option.
3. Check the Output panel for any compilation errors. The errors should be listed there.
4. Verify if any new tests with coded steps were added to the project. If so, ensure that they were added using the import option in Test Studio and not copied and pasted into the Windows File Explorer.
5. Open the Project Settings and switch to the "Script" tab. Note the project's namespace.
6. Review the tests listed in the compilation error and their coded files.
7. In the code-behind file of each test, check if the namespace matches the project's namespace from the settings. If not, replace it with the correct namespace.
8. Alternatively, you can change the namespace for all tests at once by opening the Project Settings, switching to the "Script" tab, and modifying the namespace there. Confirm the changes by clicking "OK".
9. Compile the project again using the "Compile All" option and ensure that the compilation is successful.
10. If the compilation is successful, upload all the changes to the Storage database using the Upload button in Test Studio. Confirm the upload by clicking "OK".
11. Finally, try running the test list remotely.

