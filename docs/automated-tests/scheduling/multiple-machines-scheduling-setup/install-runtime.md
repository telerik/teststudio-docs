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

The Storage Service, which keeps the project files and results, is the help tool for the Scheduling service. The Storage service maintains a database to store these files and the database provider, which Test Studio uses is <a href="https://www.mongodb.com" target="_blank">**MongoDb**</a>. The installation of the third party components is automatically triggered, when the Storage service is getting installed and if the install wizard detects there is no existing MongoDB installation.

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

The Execution Servers are all machines in the setup, which are connected to the Scheduling service and can execute tests. Depending on the configuration, these include the machine on which is hosted the standalone Test Studio installation (where the tests are designed) as well as the machine, which hosts the Test Studio Services.

To configure a machine as an Execution Server, you need to connect its Execution client to the Scheduling service.


[1]: /img/features/scheduling-test-runs/install-runtime/fig1.png
[2]: /img/features/scheduling-test-runs/install-runtime/fig2.png
[3]: /img/features/scheduling-test-runs/install-runtime/fig3.png
[4]: /img/features/scheduling-test-runs/install-runtime/fig4.png
[5]: /img/features/scheduling-test-runs/install-runtime/fig5.png
[6]: /img/features/scheduling-test-runs/install-runtime/fig6.png
[7]: /img/features/scheduling-test-runs/install-runtime/fig7.png
[8]: /img/features/scheduling-test-runs/install-runtime/fig8.png