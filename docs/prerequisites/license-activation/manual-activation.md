---
title: Manual Activation
page_title: Manual Activation
description: "Test Studio manual activation. I am not able to login to my account and activate Test Studio. No internet on the machine and unable to activate Test Studio. Offline Test Studio license activation"
position: 6
---
# Manual Activation of Test Studio License

You may encounter connection errors, or attempt to activate Test Studio on a machine which is not connected to the Internet. Then, you can manually activate your purchased license.

Please note that while the machine that will run Test Studio may not be connected to the Internet, you will need access on another device to the Internet and our website to complete this process.

The steps to follow for manual license activation are as follows:

- [Activate Manually](#activate-manually)
- [Generate License Key Manually](#generate-license-key-manually)
- [Finish the Offline Activation](#finish-the-offline-activation)

## Activate Manually

Start Test Studio on the machine, where this is installed and choose the _'Activate Manually'_ button in the Test Studio License Activation Wizard.

![Activate Manually](/img/general-information/installation/manual-activation/fig2.png)

The next screens provides the __Machine Key__ and __Machine Name__ information. Copy your machine key from the __Machine Key__ field for later use.

![Machine Key](/img/general-information/installation/manual-activation/fig3.png)

## Generate License Key Manually

On another machine, connected to the Internet, navigate to your Telerik account in the <a href="http://www.telerik.com/account/your-products/testing-tools-manage-license-keys.aspx" target="_blank">Test Studio License Keys Management Form</a>. Scroll down to the bottom and click  the _'+ Add a key'_ button.

![License Keys Management Form](/img/general-information/installation/manual-activation/fig4.png)

Select the purchased Test Studio version from the _'Product'_ drop down menu. Enter the machine key, copied from the machine on which is Test Studio, within the provided field, add the machine name and friendly name, then click the __'Generate Key'__ button.

![Select Product](/img/general-information/installation/manual-activation/fig5.png)

> __Note!__ There are reserved words that cannot be used for Machine key, Machine name and Friendley name. The words are **telerik**, **admin**, **administrator**, **sitefinity**, **icenium**, **kendo**, **kendoui** and **moderator**.

Once the key is generated you get a confirmation screen, from which you can copy it, and transfer the key to the machine on which is Test Studio. Use the _'copy key'_ button to copy it to the clipboard.

![Copy key](/img/general-information/installation/manual-activation/fig6.png)

## Finish the Offline Activation

Switch to the machine, which hosts the Test Studio installation and paste the manually generated registration key from your Telerik account within the _'License Key'_ field in Test Studio License Activation Wizard, then click the __'Activate'__ button.

![Activate](/img/general-information/installation/manual-activation/fig7.png)

## Report Possible Troubles

If you run into an issue using the manual activation wizard, please send an email to [sales@telerik.com](mailto:sales@telerik.com). Make sure your email contains:

* Email address on account.
* Machine info key.
* A copy of any error message you are receiving while trying to activate your software.
* A screenshot of the issue (if possible, must be in .jpg/.png/.gif format).