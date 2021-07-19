---
title: Configure a Test Studio Storage Server
page_title: Configure a Test Studio Storage Server
description: "Create a Test Studio Storage Server. The Telerik storage service is responsible for handling tests and test results for scheduled test runs in remote machine execution setup. Storage server uses MongoDb as storage database"
position: 2
publish: false
---
# Configure a Machine to Act as a Storage Server

In a distributed Test Studio installation, the Storage Server is responsible for handling tests and test results for scheduled test runs. It does not need to be on the same machine as any other service or application, although it must be accessible from the <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling Server</a>.

## Install the Test Studio Storage Service

If you decide to host the Storage service on a separate machine, you need to install **minimum the Test Studio Run-time edition** on this computer. Ensure to include the Storage Service component in the **Customize Installation dialog** in the installation wizard.

![Installation Dialog][1]

> **Note!** The Test Studio services are **not selected** in a default Test Studio Standalone installation and **are installed by default** when installing the Run-time Test Studio edition.

### MongoDB Installation

The Test Studio Storage Service is using <a href="https://www.mongodb.com" target="_blank">**MongoDb</a> as storage database**. The installation wizard performs a check if there is an existing installation of MongoDB on the machine. If this is first time installation of any Test Studio component, the wizard will need to install the MongoDB as well. Once prompted, agree to the MongoDB license agreement and its download and installation will start automatically.

![License Agreement][8]

Test Studio will install and configure automatically the MongoDB database on the current machine.

![Install MongoDB][9]

> **Note!** Please, note that MongoDb requires at least 4Gb hard drive space to operate normally.

## Configure the Test Studio Storage Service

The Test Studio Storage Service is being <a href="/features/scheduling-test-runs/multiple-machines-scheduling-setup/create-scheduling-server#storage-tab" target="_blank">configured together with the Scheduling one</a>.

[1]: /img/features/scheduling-test-runs/create-storage-server/fig1.png
[8]: /img/features/scheduling-test-runs/create-storage-server/fig1new.png
[9]: /img/features/scheduling-test-runs/create-storage-server/fig2new.png