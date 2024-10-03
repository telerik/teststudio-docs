---
title: Handling If..Else Step Failures with Conditional Steps in Test Studio
description: Learn how to troubleshoot and resolve issues where an 'if..else' step fails to execute in conditional logic within Telerik Test Studio.
type: troubleshooting
page_title: Troubleshoot and Fix If..Else Step Execution Problems in Test Studio Conditional Steps
slug: if-else-step-failure-test-studio
tags: [test studio, conditional step, troubleshooting, waitforexist, verify]
res_type: kb
ticketid: 1666167
---

## Description
When implementing a conditional logic statement in a test, such as an if...else statement, the "else" step fails to execute as expected. This issue occurs when using steps like "wait for exist," "verify is enabled," or "verify is visible." Specifically, the test keeps waiting for an element until it times out and never proceeds to the "else" step, even when the conditional element does not exist on the page.

## Cause
This issue often arises due to how Test Studio handles element images in steps. Test Studio records images for all elements with few exceptions. For instance, an element recorded for a `WaitForExist` step does not capture an image. The default settings use the image as a backup search method in case the find expression doesn't match an element on the current page. If the element is not found in the DOM using its find expression, the backup search option gets triggered, potentially causing the step to fail incorrectly if the backup image does not match the actual page content.

## Solution
To resolve this issue, consider the following approaches:

### Record a New WaitForExist Step
1. Record a new `WaitForExist` step directly from the browser. This ensures the element will be newly referenced in the project without an associated image.
2. Replace the existing conditional step with the newly added `WaitForExist` step.

### Modify or Remove the Image for the Step
1. If you prefer to keep the test as it is, you can modify the image associated with the step. Navigate to the element's properties and edit the image to either accurately match the actual element or remove the image entirely for the `WaitForExist` step.
2. To edit the image, follow the instructions on how to [edit an image in elements edit mode](https://docs.telerik.com/teststudio/automated-tests/elements/find-element-by-image#edit-image-in-elements-edit-mode) and how the image is referenced to the steps.
3. Alternatively, you can [record a new image](https://docs.telerik.com/teststudio/automated-tests/elements/find-element-by-image#recording-new-image) that accurately reflects the element you are trying to wait for or verify.

Implementing either of these solutions should allow the conditional logic to execute correctly, proceeding to the "else" step when the conditional element does not exist.

## See Also
- [Failure Reason Section](https://docs.telerik.com/teststudio/automated-tests/test-results/step-failure-details#failure-reason-section)
- [Elements Image and Find Expression](https://docs.telerik.com/teststudio/automated-tests/elements/elements-find-expression#elements-image)
- [Element Image Known Scenarios](https://docs.telerik.com/teststudio/knowledge-base/test-recording-kb/element-image-known-scenarios)
- [Project Settings - Element Images](https://testdocs.telerik.com/teststudio/features/project-settings/element-images)
- [Find Element by Image](https://docs.telerik.com/teststudio/automated-tests/elements/find-element-by-image#edit-image-in-elements-edit-mode)
