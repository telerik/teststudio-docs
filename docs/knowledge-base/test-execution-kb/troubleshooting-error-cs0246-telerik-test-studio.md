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
When trying to compile Test Studio project I get error CS0246. The error prevents me running a test list remotely or locally. The error persists even when I try to run a single test using the Execute button.

```
[ Compiler ]
12:14:49 'ERROR' > C:\Test Studio Projects\TestProject27\getBaseUrl.tstest.cs(39,16) : error CS0246: The type or namespace name 'Pages' could not be found (are you missing a using directive or an assembly reference?)
12:14:49 'ERROR' > C:\Test Studio Projects\TestProject27\getBaseUrl.tstest.cs(32,17) : error CS0246: The type or namespace name 'Pages' could not be found (are you missing a using directive or an assembly reference?)
12:14:49 'INFO' > Build Failed

```

## Solution
To resolve this compilation CS0246 error, follow these steps:

1. Open the project in Telerik Test Studio.
2. <a href="/automated-tests/coded-tests/compile-project" target="_blank">Compile the project</a> by selecting the "Compile All" option. 
3. Check the <a href="/automated-tests/coded-tests/output-panel" target="_blank">Output panel</a> for any compilation errors. The errors are listed there.
4. Verify if any new tests with coded steps were added to the project. If so, ensure that they were <a href="/knowledge-base/best-practices-kb/add-existing-test" target="_blank">added using the import option</a> in Test Studio and not copied and pasted into the Windows File Explorer.
5. Open the Project Settings and switch to the <a href="/features/project-settings/script-options" target="_blank">"Script" tab</a>. Note the project's namespace.
6. Review the tests listed in the compilation error and their coded files.
7. In the code-behind file of each test listed in the compilation error, check if the namespace matches the project's namespace from the settings - replace it with the current namespace.
8. Alternatively, you can change the namespace for all tests at once by opening the Project Settings, switching to the "Script" tab, and modifying the namespace there. Confirm the changes by clicking "OK".
9. Compile the project again using the "Compile All" option and ensure that the compilation is now successful.
