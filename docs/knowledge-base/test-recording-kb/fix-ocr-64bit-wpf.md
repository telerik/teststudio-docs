---
title: Fix Optical Character Recognition for 64bit WPF Applications
page_title: Fix OCR for 64bit WPF Applications
description: Fix OCR recording and execution for 64bit WPF applications. Optical Character Recognition OCR for WPF applications 64 bit. Test Studio release 2020 R2 fix for OCR for WPF application.
position: 3
---
# Fix Optical Character Recognition (OCR) Recording and Execution for 64bit WPF Applications

The new OCR feature in Test Studio was release in 2020 with R2. You can extract the text from image and use it in verification, wait of extract steps.

## Problem

Lets start by saying that this issue applies only for Test Studio Release 2 and the following Service Pack 1 from 2020 and is fixed with the installation of later versions. If you have version of Test Studio 2020.3 or higher, you should not experience this issue.

When automating a 64bit WPF application with Test Studio, you might encounter some issues recording and executing OCR steps. Those are the OCR steps from the <a href="/features/recorder/verifications/text-from-image#how-to-record-a-text-from-image-step" target="_blank">Quick Steps</a> menu, or the <a href="/features/custom-steps/overview" target="_blank">Step Builder</a>. The steps will not be added to the WPF test, because of a missing assembly in the installed Test Studio application. Even if you managed to add them on another machine, you won't be able to execute them successfully. 

## Solution

Add the missing assemblies to your current installation of Test Studio. Download the necessary assemblies from <a href="/downloads/OCR_tessaract.4.1.0x64.zip" target="_blank">**here**</a> and paste the unzipped "x64" folder in the following two places.
- In the **\Bin** folder of your Test Studio installation, which is "C:\Program Files (x86)\Progress\Test Studio\Bin" by default.
- In the **\Bin\Plugins\TFS** folder of your Test Studio installation, which is "C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\TFS" by default.

Close all Test Studio processes and that should fix the recording and execution of OCR steps against 64bit WPF application.
