---
title: Cannot Add Open Test
page_title: Cannot Add Open Test
description: "Learn how to resolve issues when adding or opening tests in Visual Studio with the Test Studio plugin. This article covers common error messages, troubleshooting steps, and best practices for managing test files and projects."
position: 1
---
# Cannot Add Open Test

## PROBLEM

When trying to open an existing test with the Visual Studio plugin, it is possible to receive the following message:

*The operation could not be completed.*


## SOLUTION

Take these steps first:

1.&nbsp; Exclude the test from the project (right click it and select Exclude From Project).

2.&nbsp; Save and close the solution.

3.&nbsp; Close and restart Visual Studio.

4.&nbsp; Reopen the solution.

5.&nbsp; Add the test back to the project.

 

If that does not work, or only works temporarily, then follow these steps:

1.&nbsp; Uninstall Test Studio.

2.&nbsp; Uninstall Visual Studio.

3.&nbsp; Reboot.

4.&nbsp; Install Visual Studio (and any applicable Service Packs).

5.&nbsp; Install Test Studio.

## PROBLEM

When trying to open or add a test to a Solution, it is possible to receive the following message:

![Error][1]

This issue can occur when you:


- Create a new, empty project/solution and try to add a test to it (before creating a test project in the solution).

- Attempt to add a test to a part of the solution that is not a Test Project.

- Attempt to open a test from source control.


## SOLUTION

A test cannot be within any part of the solution; it must be contained within a Test Project. This message will continue to display until you add a Test Project to the Solution, and then add the test to the newly created Test Project.

First add a Test Project that will contain the test, then add the test to the Test Project.

1.&nbsp; Click **File > Add > New Project**. 

![New Project][2]

2.&nbsp; On the left column, click the **Test** option. 

![Test][3]

3.&nbsp; Highlight **Test Project**. 

4.&nbsp; Click **Add**. 

5.&nbsp; Allow time for the test project to load. 

![Existing Item][4]

6.&nbsp; Right-Click the Test Project. 

7.&nbsp; Select **Add**, then choose **New Test** or **Existing Item**. 

8.&nbsp; Navigate to the folder that contains your test and .resx file (both will be required to add/use the test).

![Add Test][5]

9.&nbsp; Click the Add button. The test and resource files are added to your test.

If you forget to select the .resx or .cs file, you are prompted to locate it after adding the test file.

![Locate file][6]

Click **Yes**, then use the browsing dialog to locate the correct .resx file (the name should match the test name, only the extensions differ).

If you click **No**, you are given this message:

![New Resource][7]

If you choose to not add the file again (by clicking **Yes**), a new .resx/ file is generated (it contains the Storyboard images), but existing steps are not affected. Select No to use the above process to add an Existing Item to the test (and target the .resx file). If you have a code-behind file for the test, you will be asked to locate this as well (like the .resx file just mentioned). If you do not locate your code-behind file, the coded steps are deleted from the test entirely.

[1]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig1.png
[2]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig2.png
[3]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig3.png
[4]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig4.png
[5]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig5.png
[6]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig6.png
[7]: /img/troubleshooting-guide/visual-studio-tg/cannot-add-open-test/fig7.png
