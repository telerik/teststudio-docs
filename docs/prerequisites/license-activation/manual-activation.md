---
title: Manual Activation
page_title: Manual Activation
description: "Test Studio manual activation. I am not able to login to my account and activate Test Studio. No internet on the machine and unable to activate Test Studio. Offline Test Studio license activation"
position: 6
---
# Manual Activation of Test Studio License

The Manual License activation allows you to activate the product on a machine without access to the Internet or with restricted connection through the tool. 

The steps to follow for manual license activation are as follows:

- [Activate Manually](#activate-manually)
- [Generate License Key Manually](#generate-license-key-manually)
- [Finish the Offline Activation](#finish-the-offline-activation)

> __Note__ 
> 
> While the machine that runs Test Studio may not be connected to the Internet, you need access on another device to the Internet and our website to complete the activation process.

## Activate Manually

Start Test Studio product to launch the __Activation Wizard__ asking for login credentials. Choose the __Activate Manually__ button to get the needed identification details. 

![Activate Manually](/img/prerequisites/license-activation/manual-activation/fig1.png)

On the next screen are listed the __Machine Key__ and __Machine Name__ identifiers. You need these identifiers to generate the license key manually from your Telerik account.

![Machine Key](/img/prerequisites/license-activation/manual-activation/fig2.png)

## Generate License Key Manually

On another machine, connected to the Internet, navigate to your Telerik account in the <a href="http://www.telerik.com/account/your-products/testing-tools-manage-license-keys.aspx" target="_blank">Test Studio License Keys Management Form</a>. Scroll to the purchased license you need to activate and click the _'Add new key'_ button.

![License Keys Management Form](/img/prerequisites/license-activation/manual-activation/fig3.png)

Enter the machine key, copied from the machine on which is Test Studio, type the machine name and friendly name for it, then click the __'Generate Key'__ button.

![Select Product](/img/prerequisites/license-activation/manual-activation/fig4.png)

> __Note!__ There are reserved words that cannot be used for Machine key, Machine name and Friendly name. The words are **telerik**, **admin**, **administrator**, **sitefinity**, **icenium**, **kendo**, **kendoui** and **moderator**.

Once the key is generated you get a confirmation notification. To copy the generated key click on the _View key_ button and use the _Copy and close_ button. Paste the key onto a text document to transfer it to the machine on which is Test Studio.

![Copy key](/img/prerequisites/license-activation/manual-activation/fig5.png)

## Finish the Offline Activation

Switch to the machine with the Test Studio installation and paste the registration key within the __License Key__ field in Test Studio License Activation Wizard, then click the __Activate__ button.

![Activate](/img/prerequisites/license-activation/manual-activation/fig6.png)

## Report Possible Troubles

If you run into an issue using the manual activation wizard, please send an email to [sales@telerik.com](mailto:sales@telerik.com). Make sure your email contains:

* Email address on account.
* Machine info key.
* A copy of any error message you are receiving while trying to activate your software.
* A screenshot of the issue (if possible, must be in .jpg/.png/.gif format).