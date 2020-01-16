---
title: Installation of Test Studio Run-time Edition
page_title: Installation of Test Studio Run-time Edition
description: "Install Test Studio run-time and setup machines for remote scheduled execution"
position: 0
---
# Install Test Studio Run-time Edition

As a minimum requirement to set up multiple machines to execute Test Studio tests, you need to install the <a href="/general-information/test-studio-run-time" target="_blank">Run-time client</a> on the remote machines. It allows you to execute tests and is intended to be installed on build server machines or execution machines in the <a href="/features/scheduling-test-runs/overview" target="_blank">Test Studio Scheduling setup</a>.

## Download the Test Studio Run-time

The <a href="https://www.telerik.com/teststudio/test-studio-runtime" target="_blank">Run-time edition of Test Studio</a> is a separate product and can be downloaded from <a href="https://www.telerik.com/account/product-download?product=TESTSTUDIORUNTIME" target="_blank">your Telerik account here</a> once purchased.

## Install the Test Studio Run-time Edition

Start the installation file and follow the installation wizard. First step is to **read and agree to the <a href="https://www.telerik.com/purchase/license-agreement/teststudio" target="_blank">Licensing terms of Test Studio**</a>.

![License agreement][1]

### Enabled Components in Default Test Studio Run-time Installation

The default installation of the Run-time edition **includes the Test Studio Services - Scheduling, Storage and Executive Dashboard**. These need to be installed on one of the machines dedicated for the Scheduling setup, which will **act as a centralized <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling server**</a> and will control the communication between all machines in the configuration. If this is the particular machine, proceed by pressing the *Install* button.

![Default installation][2]

### Customize Test Studio Run-time Installation

Alternatively, in case the current machine will be only **used as an <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-execution-server" target="_blank">Execution server**</a>, you can modify the installation of the Run-time edition and **disable the Test Studio Services** from the installation wizard by pressing the *Customize* button.

![Customize installation][3]

You can choose a single component to not be installed or disable multiple features to not be included in the installation.

![Remove Single component][4]

![Remove multiple components][5]

In the *Customize* section you **can also change the default installation folder** if necessary.

![Modify Installation path][6]

### Finish Test Studio Run-time Installation

Confirm the applied changes by pressing the *OK* button and **check the list of enabled components**. Proceed with installation by pressing the *Install* button.

![Perform installation][7]

Once the wizard is ready with the installation of the selected components, you can choose whether to start the Test Studio services configurator (if these were installed). Alternatively, you can disable the check box and exit the installation wizard by pressing the *Finish* button.

![Finish installation][8]

## Upgrade Test Studio Run-time Edition

The Run-time has no built-in functionality to check for updates and installing a newer version should be manually performed. You can login to your Telerik account and open the *Downloads* section. Alternatively, you can use <a href="https://www.telerik.com/account/product-download?product=TESTSTUDIORUNTIME" target="_blank">this link</a> and download the latest available version in your account. Running the installation file will upgrade the existing version if the product is already installed on the machine.

[1]: /img/features/scheduling-test-runs/install-runtime/fig1.png
[2]: /img/features/scheduling-test-runs/install-runtime/fig2.png
[3]: /img/features/scheduling-test-runs/install-runtime/fig3.png
[4]: /img/features/scheduling-test-runs/install-runtime/fig4.png
[5]: /img/features/scheduling-test-runs/install-runtime/fig5.png
[6]: /img/features/scheduling-test-runs/install-runtime/fig6.png
[7]: /img/features/scheduling-test-runs/install-runtime/fig7.png
[8]: /img/features/scheduling-test-runs/install-runtime/fig8.png