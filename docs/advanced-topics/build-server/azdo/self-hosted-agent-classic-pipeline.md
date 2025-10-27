---
title: AzDO Classic Pipeline Using Self-Hosted Agent
page_title: Test Studio Tests in Azure DevOps Classic Pipeline Using Self-Hosted Agent
description: "Integrate Test Studio tests in Azure DevOps continuous integration. Execute Test Studio tests from an Azure DevOps Build Pipeline configured with self-hosted agent."
position: 1
---

# Test Studio Tests in Azure DevOps Classic Pipeline Using Self-Hosted Agent

<a href="https://www.telerik.com/teststudio" target="_blank">Test Studio</a> tests can be successfully integrated for execution with the Azure DevOps pipelines. This article guide you through an example setup of classic pipeline using self-hosted agent machine. 

> __Tip!__
><br>
> Double check if you have covered all prerequisites for this setup. 

## Create Classic Pipeline

1. In the Azure DevOps project go to **Pipelines >> New Pipeline**.

    ![Create new Pipeline][9]

2. For this setup choose the option to **Use the classic editor**.

    ![Choose classic editor][10]

3. Choose the repository type where the project is and fill in the necessary details to connect to the repo. Click **Continue**.

    ![Choose repo type][11]

4. Choose **Empty job** as a template for the build

    ![Choose empty job][12]

5. Click the __Pipeline__ tile and set a meaningful name for the pipeline. Then select the __Agent pool__ for self-hosted agents configured earlier.

    ![Set name and select agent pool for the pipeline][13]

6. Continue with adding the Agent tasks as described below. 

    > __Tip__
    ><br>
    > Set __all tasks__ to **Continue on error** in the task **Control Options** section. This ensures that result upload tasks run even if a previous task fails. 
    ><br>
    ><br>
    > All tasks, except the first Command Line task which executes the test run command, are optional. 

## Add Command Line Agent Task to Execute Test or Test List

1. Click the __Agent__ tile and create a new __Utility >> Command line__ task.

    ![Command line new task][14]

2. Set a meaningful name for the __Command Line__ task. Then place a command which calls the <a href="/features/test-runners/artoftest-runner" target="_blank">Test Studio CLI Runner</a> to trigger the test execution. 

    > __Tip__
    > <br>
    > Test Studio CLI runner is called __ArtOfTest.Runner.exe__ and provides various execution options. If you are not yet familiar with these check the <a href="/features/test-runners/artoftest-runner#options-to-specify-which-file-to-execute" target="_blank">CLI runner syntax options here</a> to build your command. 
   
3. The sample image executes a test list, sets specific name for the output Test Studio result file and also generates a _junit_ type of result. 

    ![Execute test list task][15]

## Add Publish Test Results Task to Upload JUnit Results

1. Click the __Agent__ tile and create a new __Tests >> Publish Test Results__ task.

    ![Add Publish Test results task][17]

2. Test Studio CLI runner lets you output the execution result in _junit_ format and this is the type of result which can be used in this pipeline task. 
   
3. Set a meaningful name for the **Publish Test Results**. Then set the folder where the test results are deployed and choose to upload all .xml files. 

    ![Configure Publish Test results][18]

4. Once the pipeline run is complete the details from _junit_ result are visible in the **Test** tab.

    ![See test results][19]

## Add Publish Pipeline Artifacts Task to Upload the Test Studio Result File 

Test Studio test run produces its own test result file which contains additional useful information for the test run. That result file can be very helpful in the case when a test run fails. The __result file always ends with file extension *.aiiresult__ and we recommend to <a href="/features/test-runners/artoftest-runner#result-option" target="_blank">specify its name as part of the command which triggers the CLI runner</a> in order to upload it to the pipeline artifacts. 

1. Click the __Agent__ tile and create a new __All >> Publish Pipeline Artifacts__ task.

    ![Add Publish Pipeline Artifacts task](/img/advanced-topics/build-server/azure-devops/fig20.png)

2. Set a meaningful name for the **Publish Pipeline Artifacts** task. Then specify the file to upload using the predefined name set in the execution command and define a meaningful name for the artifact.

    ![Configure Publish Pipeline Artifacts task](/img/advanced-topics/build-server/azure-devops/fig21.png)

3. Once the pipeline run is complete the artifacts are accessible under the __Summary__ tab in the __Related__ listings. 

    ![See published Artifacts](/img/advanced-topics/build-server/azure-devops/fig22.png)

## Add Publish Pipeline Artifacts Task to Upload the Test Studio Failure Details When Available 

Test Studio test run produces its own <a href="/automated-tests/test-results/step-failure-details" target="_blank">failure details</a> in case a test run fails. These provide additional context for the specific failure and are very useful for debugging a failing test. The failure details are output in a folder which has the name of the test result and ends with __*\_files__. Since __these are available only if a test fails__ you need to setup a task to check if such folder exists and upload the artifacts only if it does. 

1. Click the __Agent__ tile and create a new __Utility >> Command line__ task.

    ![Command line new task][14]

2. Set a meaningful name for the __Command Line__ task. Then place a command which checks for the folder using the predefined name of the result file set in the execution command and returns true or false depending on the outcome. 

    ![Script to check if a folder exists and set](/img/advanced-topics/build-server/azure-devops/fig23.png)

3. Click the __Agent__ tile and create a new __All >> Publish Pipeline Artifacts__ task.

    ![Add Publish Pipeline Artifacts task](/img/advanced-topics/build-server/azure-devops/fig20.png)

4. Set a meaningful name for the **Publish Pipeline Artifacts** task. Then specify the folder to upload using the predefined name set in the execution command adding the ending __*\_files__ and define a meaningful name for the artifact.

    ![Configure Publish Pipeline Artifacts task for the failure details](/img/advanced-topics/build-server/azure-devops/fig24.png)

5. This task is supposed to be executed only if the failure folder exists. Therefore you need to __specify a custom condition for executing the task__. Expand the __Control Options__ section of the task and set the __Custom Condiition__ to check the result of the previous __Command Line__ task. 

    ![Configure control options for Publish Pipeline Artifacts task for the failure details](/img/advanced-topics/build-server/azure-devops/fig25.png)

6. Once the pipeline run is complete the artifacts are accessible under the __Summary__ tab in the __Related__ listings. 

    ![See published Artifacts](/img/advanced-topics/build-server/azure-devops/fig22.png)



[1]: /img/advanced-topics/build-server/azure-devops/fig1.png
[2]: /img/advanced-topics/build-server/azure-devops/fig2.png
[3]: /img/advanced-topics/build-server/azure-devops/fig3.png
[4]: /img/advanced-topics/build-server/azure-devops/fig4.png
[5]: /img/advanced-topics/build-server/azure-devops/fig5.png
[6]: /img/advanced-topics/build-server/azure-devops/fig6.png
[7]: /img/advanced-topics/build-server/azure-devops/fig7.png
[8]: /img/advanced-topics/build-server/azure-devops/fig8.png
[9]: /img/advanced-topics/build-server/azure-devops/fig9.png
[10]: /img/advanced-topics/build-server/azure-devops/fig10.png
[11]: /img/advanced-topics/build-server/azure-devops/fig11.png
[12]: /img/advanced-topics/build-server/azure-devops/fig12.png
[13]: /img/advanced-topics/build-server/azure-devops/fig13.png
[14]: /img/advanced-topics/build-server/azure-devops/fig14.png
[15]: /img/advanced-topics/build-server/azure-devops/fig15.png
[16]: /img/advanced-topics/build-server/azure-devops/fig16.png
[17]: /img/advanced-topics/build-server/azure-devops/fig17.png
[18]: /img/advanced-topics/build-server/azure-devops/fig18.png
[19]: /img/advanced-topics/build-server/azure-devops/fig19.png



    

