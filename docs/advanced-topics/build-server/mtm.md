---
title: Microsoft Test Manager
page_title: Microsoft Test Manager
description: "Integrate Test Studio tests in MTM continuous integration. Execute Test Studio tests with MTM."
position: 12
publish: false

---
# Run Telerik Tests Through МТМ

*I want to run my Telerik tests through Microsoft Test Manager*

## Solution

Table of Contents:

* <a href="/advanced-topics/build-server/mtm#project-settings">Project settings</a>
* <a href="/advanced-topics/build-server/mtm#create-and-configure-tfs-build-definition">Create and configure TFS build definition</a>
* <a href="/advanced-topics/build-server/mtm#create-test-cases">Creating test cases</a>
* <a href="/advanced-topics/build-server/mtm#associate-test-case">Associating tests to test cases</a>
* <a href="/advanced-topics/build-server/mtm#create-a-new-environment">Create a new environment</a>
* <a href="/advanced-topics/build-server/mtm#add-test-cases">Add test cases to the Test Plan</a>
* <a href="/advanced-topics/build-server/mtm#runnin-a-test">Running a test</a>
* <a href="/advanced-topics/build-server/mtm#viewing-test-results">Viewing test results</a>

### Create Test Studio Project and TFS Build

1.&nbsp; <a name="project-settings"></a>Create a Progress Test Studio project and connect it to TFS. 

**Specific settings for Test Studio project:**

* Set “*Copy to Output Directory*” property to “**Copy Always**” for all files e.g. *.tstest files, data files, independent code files e.t.c. This will ensure all files needed for the build to be pulled from TFS.

![Copy always][1]

* If there are tests called as Test As Steps, external references or data files which are used in Test As Step they should be configured for the Test in Deployment items. 
	
![Deplyment item][2]

**Note:** In order to see Test Studio test properties create a **.vsmdi** file. Select a test from the Test List Editor and you will find the Test Properties.

*  <a href="/getting-started/test-execution/visual-studio-test-list" target="_blank">Visual Studio 2010</a>
*  <a href="/getting-started/test-execution/visual-studio-2012-and-later-test-list" target="_blank">Visual Studio 2012 and later</a>

2.&nbsp; <a href="https://msdn.microsoft.com/en-us/library/ms181716.aspx" target="_blank" id="create-and-configure-tfs-build-definition">Create and configure TFS build definition</a> which MTM needs for execution the tests.

**Specific settings for Test Studio project:**

* Edit the build definition to include the source with the Test Studio project solution.

![Items to build][3]

* <a name="create-test-cases"></a>Create a new Work Item of type Test Case in TFS which is your solution connected to. Choose work item under Team Explorer and click New Work Item of type Test Case.

![Test case][4]

* <a name="associate-test-case"></a>Associate Test Case automation property to point to the Progress Test Studio test *.tstest. This will ensure that the TFS Test Case is using automation test when run through MTM.

![Association][5]

> You should install <a href="/general-information/test-studio-run-time" target="_blank">Telerik Test Sutudio Runtime</a> edition on the TFS Build Controler/Agent machine. This will ensure the build will succeed and recognize Telerik Test Project when pulled out from TFS.

### Run Tests in MTM

1.&nbsp; First you should configure and register the <a href="https://msdn.microsoft.com/en-us/library/hh546460.aspx" target="_blank">MTM Controller</a> and <a href="https://msdn.microsoft.com/en-us/library/dd648127.aspx" target="_blank">Agent</a>.

2.&nbsp; <a href="https://msdn.microsoft.com/en-us/library/dd380739.aspx" target="_blank">Run MTM and connect it to the team project from TFS</a> where your project is.

3.&nbsp; <a href="https://msdn.microsoft.com/en-us/library/ee390842.aspx" target="_blank" id="create-a-new-environment">Create new environment in MTM Lab Center.</a>

**Specific settings:**

* Select *Desktop client* for machine role.

![Desktop role][9]

* In the *Advanced* section check *Configure environment to run UI* tests check box and enter the proper credentials.

![UI][10]   

> You should install <a href="/general-information/test-studio-run-time" target="_blank">Telerik Test Sutudio Runtime</a> edition on both MTM Controller and MTM Agent machines.

**Note:** When you install Progress Test Studio Runtime on the Test Controller/Agents machines you have to stop them, unregister and register again (unregister Agent from Controller and Controller from TFS team project), so the new Telerik installation is recognized by them.

4.&nbsp; <a href="https://msdn.microsoft.com/en-us/library/vstudio/dd286583(v=vs.110).aspx" target="_blank">Create a Test Plan in MTM</a> in Testing Center.

![Create plan][6]

5.&nbsp; <a name="add-test-cases"></a>In the new Test Plan add the TFS Test Cases which you have already created and contain Test Studio automation associated tests.

![Add test cases][7]


6.&nbsp; Click RUN button to pull out the test cases and add the ones you need.

![Run][8]

7.&nbsp; <a name="runnin-a-test"></a>Trigger a Run with Options for the selected TFS Test Case that has Test Studio .tstest as automation for it. This will run the TFS Work Item of type Test Case with associated automation test from Progress Test Studio (*.tstest) automatically on the MTM Test Agent.

![Run with options][11]

8.&nbsp; Select the already created build, environment and run the tests.

![Build][12]

9.&nbsp; <a name="viewing-test-results"></a>After the test completion press refresh button to see the results. MTM creates also a .trx file in the Attachments section.

![Test Results][13]

[1]: /img/advanced-topics/build-server/mtm/fig1.png
[2]: /img/advanced-topics/build-server/mtm/fig2.png
[3]: /img/advanced-topics/build-server/mtm/fig3.png
[4]: /img/advanced-topics/build-server/mtm/fig4.png
[5]: /img/advanced-topics/build-server/mtm/fig5.png
[6]: /img/advanced-topics/build-server/mtm/fig6.png
[7]: /img/advanced-topics/build-server/mtm/fig7.png
[8]: /img/advanced-topics/build-server/mtm/fig8.png
[9]: /img/advanced-topics/build-server/mtm/fig9.png
[10]: /img/advanced-topics/build-server/mtm/fig10.png
[11]: /img/advanced-topics/build-server/mtm/fig11.png
[12]: /img/advanced-topics/build-server/mtm/fig12.png
[13]: /img/advanced-topics/build-server/mtm/fig13.png