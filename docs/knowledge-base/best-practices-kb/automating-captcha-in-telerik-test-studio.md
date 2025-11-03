---
title: Automating Captcha in Telerik Test Studio
description: Learn possible solutions for handling Captcha during automation testing in Telerik Test Studio.
type: how-to
page_title: Handling Captcha Challenges in Automation Using Telerik Test Studio
meta_title: Handling Captcha Challenges in Automation Using Telerik Test Studio
slug: automating-captcha-in-telerik-test-studio
tags: telerik test studio, captcha, automation, find logic, search by image
res_type: kb
ticketid: 1675222
---


## Description

I need to automate a process that involves solving a Captcha as part of the steps. Is there any solution or workaround to achieve this during automation testing?

This knowledge base article also answers the following questions:
- How to bypass Captcha during automation testing?
- What are the options for handling Captcha in Telerik Test Studio?
- Can Captcha be automated in test environments?

## Solution

Captchas are specifically designed to prevent automation for security purposes, including tools like Telerik Test Studio. However, there are alternative approaches you can consider during testing:

1. **Whitelist Company Test IP:** Add your company's or test machine’s IP to the trusted list to bypass Captcha verification during testing.

2. **Disable Captcha in Test Environment:** Turn off Captcha in testing environments such as staging or development while keeping it enabled in production.

3. **Use Image-Based Element Identification:** For certain weak Captchas, you might use image-based element identification. This should only be a last resort if other options are unavailable.

   - To identify an element by image for a single test step, enable `SearchByImageFirst` in the [step properties](/features/test-maintenance/test-step-properties).  
   - To set image-based identification for the entire project, enable the checkbox `Search by image first` in the [Find Logic project settings](/features/project-settings/find-logic).  

   Learn more about [element identification by image](/automated-tests/elements/elements-find-expression#elements-image).

Discuss the most suitable approach with your development team to align with your requirements.

## See Also

- [Step Properties in Telerik Test Studio](/features/test-maintenance/test-step-properties)
- [Find Logic Project Settings](h/features/project-settings/find-logic)
- [Element Identification by Image in Telerik Test Studio](/automated-tests/elements/elements-find-expression#elements-image)
