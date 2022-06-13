---
title: How to Troubleshoot Failing Verification Step 
page_title: How to Troubleshoot Failing Verification Step?
description: "Learn how to debug a failing verification step in Test Studio. Understand what causes the test to fail and what troubleshooting are available to you when dealing with a failing verification." 
position: 2
---
# Troubleshoot Failing Verification

In some cases when a verification step fails, you need only to check and update the verification condition. To do this, use the __Sentence Verification Builder__ in the __Step Failure Details__ dialog.

## Update the Failing Verification

Inspect the <a href="/automated-tests/test-results/step-failure-details" target="_blank">Step Failure Details</a> section for the failing verification step and use either the __Resolve Failure__ or __Update Verification__ button to open the __Sentence Verification Builder__.

![Update Verification step](/img/automated-tests/troubleshooting/update-verification/1Buttons.png)

Once the __Sentence Verification Builder__ appears, click the _pen_ icon to edit the value.

![Update Verification step](/img/automated-tests/troubleshooting/update-verification/2EditValue.png)

Save the changes and then execute the test to verify that it passes.

> __Note__
><br>
><br>
> If a <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification#how-to-record-an-image-verification-step" target="_blank">Verify image step</a> fails, the __Resolve Failure__ and __Update Verification__ buttons do not appear. In this case, re-record the step or <a href="/automated-tests/elements/find-element-by-image#recording-new-image" target="_blank">update the image associated with the step</a>.
