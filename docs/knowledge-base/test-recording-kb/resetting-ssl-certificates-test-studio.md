---
title: Resetting SSL Certificates to Resolve Performance Run Errors in Telerik Test Studio
description: Learn how to reset SSL certificates to resolve performance run errors in Telerik Test Studio caused by FiddlerCore certificate issues.
type: how-to
page_title: Resolving SSL Certificate Errors in Telerik Test Studio Performance Runs
meta_title: Resolving SSL Certificate Errors in Telerik Test Studio Performance Runs
slug: resetting-ssl-certificates-test-studio
tags: telerik test studio, ssl, fiddler, performance, certificate
res_type: kb
ticketid: 1576623
---


## Description

I encountered an SSL certificate error while running performance tests in Telerik Test Studio. The issue seems related to the FiddlerCore engine used in the background by Test Studio. Fiddler certificates might be improperly configured or corrupted, causing the connection to not be trusted.

This knowledge base article also answers the following questions:
- How to reset Fiddler SSL certificates for Telerik Test Studio?
- How to resolve SSL errors in Test Studio performance mode?
- How to fix SSL certificate issues affecting Test Studio tests?

## Solution

To fix this issue, reset the Fiddler certificates using the following steps:

1. If Fiddler Classic is installed, open it and navigate to the [Options menu](https://docs.telerik.com/fiddler/configure-fiddler/tasks/decrypthttps) (Tools > Options > HTTPS).
2. From the Actions dropdown, select "Reset All Certificates."
3. Confirm all prompts about removing existing certificates and adding new ones.
4. Ensure the prompt configuring Windows to always trust the Fiddler root certificate is confirmed.

If Fiddler is not actively used but was installed previously, remove leftover certificates manually:

1. Open the Windows Certificate Manager by typing `certmgr` in the Start menu.
2. Under "Trusted Root Certification Authorities," locate certificates named `DO_NOT_TRUST_FiddlerRoot`.
3. Remove all Fiddler-related certificates.
4. Close the Certificate Manager.

After resetting or removing certificates:
1. Open Telerik Test Studio.
2. Register the HTTPS certificate again.
3. Run tests in performance mode to confirm the issue is resolved.

## See Also

- [Decrypting HTTPS Traffic in Fiddler](https://docs.telerik.com/fiddler/configure-fiddler/tasks/decrypthttps)
- [Trusting the Fiddler Root Certificate](https://docs.telerik.com/fiddler/configure-fiddler/tasks/trustfiddlerrootcert) 
- [Telerik Test Studio Documentation](https://docs.telerik.com/teststudio) 
