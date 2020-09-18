---
title: Fix OCR for 64bit WPF Applications
page_title: Fix OCR for 64bit WPF Applications
description: Fix OCR recording and execution for 64bit WPF applications. Optical Character Recognition OCR for WPF applications 64 bit. Test Studio release 2020 R2 fix for OCR for WPF application.
position: 3
---
# Fix Optical Character Recognition (OCR) Recording and Execution for 64bit WPF Applications

The <a href="/features/recorder/verifications/text-from-image" target="_blank">OCR feature</a> for WPF tests was introduced with Test Studio 2020 R2 SP1 (v.2020.2.910). You can extract the text from image and use it in verification, wait of extract steps.

## Problem

This issue applies only for **Test Studio 2020 R2 SP1 (v.2020.2.910)** and is fixed with the installation of later versions. If you have version of Test Studio 2020.3.x or higher, you should not experience this issue. 

When **automating a 64bit WPF application** with Test Studio, you might encounter some issues recording and executing OCR steps. Those are the OCR steps from the <a href="/features/recorder/verifications/text-from-image#how-to-record-a-text-from-image-step" target="_blank">Quick Steps</a> menu, or the <a href="/features/custom-steps/overview" target="_blank">Step Builder</a>. The steps **will not be added to the WPF test**, because of a missing assembly in the installation of Test Studio. Even if you managed to add them on another machine with higher version of Test Studio, you won't be able to execute them successfully on lower versions. 

## Solution

Add the missing assemblies to your current installation of Test Studio. You can find and download them from <a href="/downloads/OCR_tesseract.4.1.0x64.zip" target="_blank">**here**</a>. 

1. **Close all running Test Studio processes**.
2. Paste the unzipped "x64" folder in the following two places. The **%installDir%** is the installation folder of Test Studio, which by default is - "C:\Program Files (x86)\Progress\Test Studio".
3. In the **%installDir%\Bin** folder.
4. In the **%installDir%\Bin\Plugins\TFS** folder. 

The above steps should fix the recording and execution of OCR steps against 64bit WPF applications.
