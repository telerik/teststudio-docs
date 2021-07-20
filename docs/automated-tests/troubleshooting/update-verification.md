---
title: How to Troubleshoot Failing Verification Step 
page_title: How to Troubleshoot Failing Verification Step?
description: "Test Studio - debug failing verification step. How to understand what causes the test to fail. What options I have to debug or troubleshoot a failing verification. My test fails to  verify a value." 
position: 2
---
# Troubleshoot Failing Verification

In some cases when a verification step fails, you only need to check and update the verification condition. Test Studio provides direct access to verification __Sentence Verification Builder__ in the Step Failure Details.

The steps to follow for such scenario are listed in this article.

## Update the Failing Verification

Check the <a href="/automated-tests/test-results/step-failure-details" target="_blank">step failure details</a> section for the failing verification step and use one of the buttons __Resolve Failure__ or __Update Verification__ in the 3rd suggestion to open the __Sentence Verification Builder__.

![Update Verification step](/img/automated-tests/troubleshooting/update-verification/1Buttons.png)

Once __Sentence Verification Builder__ is launched, click on the _pen_ icon to edit the value.

![Update Verification step](/img/automated-tests/troubleshooting/update-verification/2EditValue.png)

Save and execute to verify the test successfully passes.

> __Note__
><br>
><br>
> Keep in mind that if <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification#how-to-record-an-image-verification-step" target="_blank">Verify image step fails</a>, __Resolve Failure__ and __Update Verification__ buttons do not appear. In this case you better re-record the step or <a href="/automated-tests/elements/find-element-by-image#recording-new-image" target="_blank">update the image associated with the step</a>.
