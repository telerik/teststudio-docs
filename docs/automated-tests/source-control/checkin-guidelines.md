---
title: Check-in Guidelines
page_title: Check-in Guidelines
description: "Test Studio specific remote repository Check-in Guidelines tips and tricks. Files to exclude from source control check in"
previous_url: /user-guide/source-control/check-in-guidelines.aspx, /user-guide/source-control/check-in-guidelines
position: 0
---
# Check-in Guidelines

## Files to Exclude from Check-in

For any source control system, check in all files **except** the following:

- Pages.g.cs (or .vb) - this file is auto-generated with every build.
- *.suo files - this is a VS per user settings file.
- Anything in the TestResults folder.
- The project *.dll file in the project bin folder - this file is auto-generated with every build.
- If you also use the Standalone version, you will want to exclude the Results folder. This folder is only created by the Standalone version and holds the results of test list runs.

## Files to Check-in

**Visual Studio test projects may also use these unique files:**

- *.vsmdi - this is a Visual Studio file. It stores the definitions of Visual Studio test lists.
- *.testsettings - this is a Visual Studio file. It stores the test run configuration settings (default timeouts, default browser, etc.).
- Files in the Properties folder - this is created for every Visual Studio project. It contains definitions for the projects assembly.

**The following files are unique to Test Studio projects:**

- *.tstest (or .aii) - these contain the actual test definitions.
- *.cs / *.vb - these contain the code for your coded steps.
- *.resx - these contain the images for the Storyboard.
- *.imgstore - these contain the images for the elements associated with the test.
- Settings.aiis - this contains properties specific to this Test Studio project (e.g. tool version it was created under, Recording settings, assembly references, TFS connection settings).
- .aiilist - these contain the test list definitions.
- .tsprofconfig files in the Profiler Configurations folder - this is where the Performance configuration settings are stored. Whether or not to check in these files into Source Control depends on whether or not you want to save/share this information.

>Note: The <a href="/features/source-control/connect-to-tfs" target="_blank">TFS Plugin</a> selects the correct files for check-in automatically.

## Upgrading a Project Which is Used by Multiple Team Members

1.&nbsp; One of the team member should check out the test project and upgrade it on his local machine.

2.&nbsp; After upgrading the project this same member should check in the upgraded project back into the source control.

3.&nbsp; The other team members now can get the latest version of the project and use it without merging conflict in the newer version of Test Studio.