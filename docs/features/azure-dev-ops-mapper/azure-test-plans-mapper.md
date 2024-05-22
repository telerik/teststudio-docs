---
title: Azure Test Plans Mapper
page_title: Azure Test Plans Mapper
description: "Learn how to use Telerik.TestStudio.AzureResultsSync.exe convert Test Studio results to Azure DevOps runs."
position: 2
---

# Azure Test Plans Mapper

**Telerik.TestStudio.AzureTestPlansMapper.exe** is GUI tool that allows you to map Test Studio test from a particular project to predefined Azure DevOps test cases.

To use the tool you will need a Azure DevOps personal access token (PAT) with full **Work Items** and **Test Management** permissions.


## Create New Mappings

1. Go to **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureTestCaseMapper** folder and start **Telerik.TestStudio.AzureTestPlansMapper.exe**. 

1. Select __'Create new'__ option and press __'Next'__ button.

    ![fig.1](/img/features/azure-dev-ops-mapper/fig1.png)

1. Enter the folder where your Test Studio project is stored locally. Press the __'Next'__ button.

    ![fig.2](/img/features/azure-dev-ops-mapper/fig2.png)

1. Specify the URL of your Azure DevOps location (e.g. https://dev.azure.com/my-org) and a valid token. Press __'Connect'__ and wait for the tool to establish connection with Azure DevOps.

    ![fig.3](/img/features/azure-dev-ops-mapper/fig3.png)

1. Once the connection is established, select the project where your test plan is located and then press __'Next'__.

    ![fig.4](/img/features/azure-dev-ops-mapper/fig4.png)

1. A mapping table is displayed. In the first column you see all tests from selected Test Studio project. The second column shows an associated test case when available.

    ![fig.5](/img/features/azure-dev-ops-mapper/fig5.png)

1. To create a new mapping between a test and a test case press the __'Map'__ button in the third column.

1. From the mapping dialog select the Azure DevOps test case and owner test suite and test plan. You can choose whether to upload artifacts like failure image and log files as well.

    ![fig.6](/img/features/azure-dev-ops-mapper/fig6.png)

1. Repeat the step above for all tests that need to be mapped. When all tests are mapped press the __‘Export'__ button to generate the mapping file needed for the results synchronization.

    ![fig.7](/img/features/azure-dev-ops-mapper/fig7.png)

1. We recommend to keep the exported mapping file in the root folder of your Test Studio project, but you have the option to choose another location on your hard drive. Finally, you see a success message.

    ![fig.8](/img/features/azure-dev-ops-mapper/fig8.png)

Congratulations! Your mapping is complete.