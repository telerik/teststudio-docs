---
title: Resolving "Error CS0246 'Pages' could not be found" in Telerik Test Studio
description: "Learn how to resolve the CS0246: The type or namespace name 'Pages' could not be found compialtion error in Telerik Test Studio when running a batch remotely or locally. "
type: troubleshooting
page_title: Troubleshooting Compile Error CS0246 in Telerik Test Studio
slug: troubleshooting-error-cs0246-telerik-test-studio
tags: telerik-test-studio, error-cs0246, troubleshooting
res_type: kb
---
# Resolve Compiler Error "Error CS0246 'Pages' could not be found"

## Description
When trying to compile Test Studio project I get error __CS0246: The type or namespace name 'Pages' could not be found__. The error prevents me running a test list remotely or locally. The error persists even when I try to run a single test using the `Execute` button.

```
[ Compiler ]
12:14:49 'ERROR' > C:\Test Studio Projects\TestProject27\getBaseUrl.tstest.cs(39,16) : error CS0246: The type or namespace name 'Pages' could not be found (are you missing a using directive or an assembly reference?)
12:14:49 'ERROR' > C:\Test Studio Projects\TestProject27\getBaseUrl.tstest.cs(32,17) : error CS0246: The type or namespace name 'Pages' could not be found (are you missing a using directive or an assembly reference?)
12:14:49 'INFO' > Build Failed

```

## Cause 

The code-behind files listed in the compilation errors have a namespace which doesn't match the project's namespace. 

## Solution

To resolve this compilation CS0246 error, follow these steps:

1. Open the project in Telerik Test Studio.
2. <a href="/automated-tests/coded-tests/compile-project" target="_blank">Compile the project</a> by selecting the "Compile All" option. 
3. Check the <a href="/automated-tests/coded-tests/output-panel" target="_blank">Output panel</a> for any compilation errors. The errors are listed there.
    
    > __Important!__
    ><br>
    ><br>
    > If the __local compilation is successful__ but you see the mendioned error when executing tests remotely via the Test Studio Scheduling setup, probably you uploaded the project to the Storage database in a corrupted state. 
    ><br>
    > - __If the test and code-behind file exists__ in the project, ensure <a href="/automated-tests/scheduling/upload-latest-files" target="_blank">to upload the latest fixed state of the project to the Storage database</a>. 
    ><br>
    > - __If the test and code-behind file doesn't exists__ in the project anymore, you will need to <a href="/knowledge-base/scheduling-kb/drop-storage-database" target="_blank">drop the database</a>.  

4. Open the Project Settings and switch to the <a href="/features/project-settings/script-options" target="_blank">"Script" tab</a>. Note the project's namespace.
5. Review the tests listed in the compilation error and their coded files.
6. In the code-behind file of each test listed in the compilation error, __check if the namespace matches the project's namespace from the settings - replace it with the current namespace__.
7. Alternatively, you can change the namespace for all tests at once by opening the Project Settings, switching to the "Script" tab, and modifying the namespace there. Confirm the changes by clicking "OK".
8. Compile the project again using the "Compile All" option and ensure that the compilation is now successful.

> __Tip__
> <br> 
> To avoid such errors ensure that you __use the option to <a href="/knowledge-base/best-practices-kb/add-existing-test" target="_blank">import existing tests</a> in a Test Studio project__ instead of copying the files in  Windows File Explorer.
