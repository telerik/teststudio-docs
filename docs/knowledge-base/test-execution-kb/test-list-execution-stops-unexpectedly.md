---
title: Test List Execution Stops Unexpectedly in Test Studio
description: Steps to diagnose and resolve issues where Test List execution halts without generating results in Telerik Test Studio.
type: troubleshooting
page_title: Resolving Test List Execution Stopping Unexpectedly Without Generating Results in Test Studio
slug: test-list-execution-stops-unexpectedly
tags: test studio, test list, execution, troubleshooting
res_type: kb
ticketid: 1677915
---


## Description

When executing a Test List in Telerik Test Studio, the execution stops unexpectedly in the middle of the test list run. The application under test is closed, and no results are generated in the designated folders, or displayed in the Results tab.

## Cause

The issue may occur due to a test referenced in the Test List being missing from the project. This situation can lead to the Test Studio Test Runner ending up the test list run without completing the execution of all tests.

The missing test is usually moved or renamed, or completely removed outside of Test Studio project - like for example, managing the test files in File Explorer. It is recommended to maintain the test files only within the Test Studio project via the [Project Explorer options](/features/project-explorer/overview#project-items-context-menu). 

## Solution

To identify and resolve the issue with the Test List execution stopping unexpectedly, follow these steps:

1. Ensure that application logging is enabled in Telerik Test Studio. For more details on how to operate with logging, refer to the [documentation](/knowledge-base/best-practices-kb/generate-application-log#operate-with-logging-in-standalone-version).

2. Clear the existing log or ensure logging is enabled, and then run the Test List again.

3. Once the execution stops unexpectedly, review the generated application log. Look for entries similar to the following error message:

    ```
    [Error] LoadTest: Unable to find test at 'C:\Test Studio\ProjectFolder\SubFolder\Test1.tstest'!
....
CommandLineTestListRunner.RunnerProcess_Exited() : Runner process exit code: 12 - NOT_RUN_TEST_NOT_FOUND.
    ```

4. This error indicates that a test referenced in the Test List (`Test1.tstest`) is missing from the specified location in the project.

5. Locate the missing test file and ensure it is properly included in the project folder. If the test cannot be recovered, consider removing or replacing its reference in the Test List.

6. After resolving the issue with the missing test, re-run the Test List to confirm that the execution completes successfully and generates the expected results and reports.

By following these steps, you should be able to diagnose and fix the issue causing the Test List execution to stop unexpectedly in Telerik Test Studio.


