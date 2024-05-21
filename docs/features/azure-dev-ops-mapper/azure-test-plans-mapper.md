---
title: Azure Test Plans Mapper
page_title: Azure Test Plans Mapper
description: "Learn how to use Telerik.TestStudio.AzureResultsSync.exe convert Test Studio results to AzureDevOps runs."
position: 3
---

# Azure Test Plans Mapper

**Telerik.TestStudio.AzureTestPlansMapper.exe** is GUI tool that allows you to map Test Studio test from a particular project to predefined AzureDevOps test cases.

To use the tool you will need a AzureDevOps personal access token (PAT) with full **Work Items** and **Test Management** permissions.


## Create new mappings

1. Go to **C:\Program Files (x86)\Progress\Test Studio\Bin\AzureTestCaseMapper** folder and start **Telerik.TestStudio.AzureTestPlansMapper.exe**. Select 'Create new' option and press 'Next' button.

![fig.1](/img/features/azure-dev-ops-mapper/fig1.png)

2. Enter the folder where your Test Studio project is located. Press the 'Next' button.

![fig.2](/img/features/azure-dev-ops-mapper/fig2.png)

3. Specify the url of your AzureDevOps location (e.g. https://dev.azure.com/my-org) and a valid token. Press 'Connect' and wait for the tool to establish connection with AzureDevOps.

![fig.3](/img/features/azure-dev-ops-mapper/fig3.png)

Once the connection is established, select the project where your test plan is located and then press 'Next'.

![fig.4](/img/features/azure-dev-ops-mapper/fig4.png)

4. A mapping table is displayed. In the first column you can see all tests from current Test Studio project. In the second column you can see the corresponding AzureDevOps test case. To create a new mapping press the 'Map' button in the third column.

![fig.5](/img/features/azure-dev-ops-mapper/fig5.png)

From the mapping dialog select your AzureDevOps test case and owner test suite and test plan. You can choose whether to upload artifacts like failure image and log files as well.

![fig.6](/img/features/azure-dev-ops-mapper/fig6.png)

Repeat the step above for all tests that need to be mapped. When all tests are mapped press the ‘Export' button.

![fig.7](/img/features/azure-dev-ops-mapper/fig7.png)

You will be asked where to store the mapping file. We recommend keeping the file in the root folder of your Test Studio project. Finally, you will see a success message.

![fig.8](/img/features/azure-dev-ops-mapper/fig8.png)

Congratulations. Your mapping is complete.