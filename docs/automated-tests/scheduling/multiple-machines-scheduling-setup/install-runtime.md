---
title: Installation of Test Studio Components
page_title: Installation of Test Studio Components
description: "Install Test Studio Services and Run-time on execution machines and setup machines for remote scheduled execution. Which machine should host the Test Studio Services? Do I need more than one machine with the Test Studio Services."
position: 0
---
# Install Test Studio Across the Machines

The Scheduling setup in Test Studio is a set of services, which allow the communication between the Test Studio components on the different machines. Depending on their role in the configuration, the machines can run different editions of the product, and can be set up in various combinations.

This article will guide you through the components and their specifics.
## __Scheduling Components__

## Scheduling Service

The Scheduling Service is the central part of the overall setup - it is in the middle of all operations and can be considered that it controls the process of running a test list on any remote machine. All machines, the Storage Service and the projects are all connected to the same Scheduling service.

- __By default it uses port 8009__, but it can be changed with any other free port in the _Scheduling config wizard_.
- Apart from the default set _localhost_, __the _Scheduling config wizard_ accepts IP address or machine name__ for accessing the computer, which hosts the Scheduling service.

## Storage Service

The Storage Service, which keeps the project files and results, is the help tool for the Scheduling service. The Storage service maintains a database to store these files and the database provides, which Test Studio uses is <a href="https://www.mongodb.com" target="_blank">**MongoDb**</a>. The installation of the third party components is automatically triggered, when the Storage service is getting installed and if the install wizard detects there is no existing MongoDB installation.

- __By default it uses port 8492__, but it can be changed with any other free port in the _Scheduling config wizard_.
- Apart from the default set _localhost_, __the _Scheduling config wizard_ accepts IP address or machine name__ for accessing the computer, which hosts the Storage service.
- The Storage Service uses the default connection string to connect to MongoDB. If you reconfigure MongoDB, you need to apply the changes in the _Scheduling config wizard_ as well.
- The Scheduler contacts the Storage Service for every scheduled job or results review. The Storage Service communicates internally to the database to provide the queried info.

## Executive Dashboard Service

The Executive Dashboard Service is the tool, which provides access to all results generated from scheduled test list runs for all team members - including these, who do not have Test Studio installed. This service keeps a _localhost_ page, which visualizes the results stored in the storage database.

- __By default it uses port 8085__, but it can be changed with any other free port in the _Scheduling config wizard_.
- The Executive Dashboard service communicates with the configured Storage service. So, if you reconfigure the Storage Service, you need to change the details for the Executive Dashboard Service as well.
- The _localhost_ page can be loaded from the _Scheduling config wizard_

## Execution Servers

The Execution Servers are all machines in the setup, which are connected to the Scheduling service and can execute tests. Depending on the configuration, these include the machine on which is hosted the standalone Test Studio installation (where the tests are designed) as well as the machine. which hosts the Test Studio Services.

To configure a machine as an Execution Server, you need to connect its Execution client to the Scheduling service.

## __Installation__

Assuming there is an automation test project to be executed you have one machine with standalone Test Studio installation - Ultimate or Web&Desktop edition. Since you always have access to this machine, it can be referred to as the local machine in the setup.

=============

As a minimum requirement to set up multiple machines to execute Test Studio tests, you need to install the <a href="/introduction/test-studio-run-time" target="_blank">Run-time client</a> on the remote machines. It allows you to execute tests and is intended to be installed on build server machines or execution machines in the <a href="/features/scheduling-test-runs/overview" target="_blank">Test Studio Scheduling setup</a>.

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