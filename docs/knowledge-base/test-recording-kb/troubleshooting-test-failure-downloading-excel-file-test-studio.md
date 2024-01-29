---
title: Troubleshooting Test Failure when Downloading Excel File
description: This article provides troubleshooting steps for resolving a test failure that occurs when attempting to download an Excel file during test execution.
type: troubleshooting
page_title: Troubleshooting Test Failure when Downloading Excel File | Test Studio | Telerik
slug: troubleshooting-test-failure-downloading-excel-file-test-studio
tags: troubleshooting, test failure, downloading, Excel file, Test Studio
res_type: kb
---

## Environment

| Property | Value                   |
|----------|-------------------------|
| Product  | Progress Telerik Test Studio |
| Version  | 2023.3.1115.3          |

## Description

When attempting to execute a test in Test Studio that includes a step to download an Excel file, the test fails with the following error:

```
System.ArgumentException: Open or Run downloaded file is not supported for ChromeHeadless.
```

This error can occur even when running the test with the regular Chrome browser, not just the headless version.

## Solution

To resolve this issue, follow these steps:

1. Open the test project in Test Studio.
2. Locate the step that downloads the Excel file.
3. In the properties of the step, ensure that the `HandleButton` property is set to "Save".
4. Save the test project.
5. Run the test again.

By setting the `HandleButton` property to "Save", Test Studio will handle the download dialog and save the file instead of attempting to open or run it, which is not supported in the Chrome browser.

If the issue persists or if you have any further questions, please let us know.

## Notes

- This solution applies to Test Studio version 2023.3.1115.3.
- If you are using a different version of Test Studio, the steps or property names may vary slightly.

## See Also

- [Downloading Files in Test Studio](https://www.telerik.com/support/kb/teststudio/general-tasks/downloading-files-in-test-studio)
