---
title: My Project Runs Locally but Does Not Remotely
page_title: My Project Runs Locally but Does Not Remotely
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: true
---

# My Project Runs Locally but Does Not Remotely #

*Apart from the communication issues that might occur in a remote setup there are few reasons related to some project specifics why a test list is successfully executed in local run but fails to be started and compiled in remote one. To easily determine whether the remote connections are successfully built create a test list with a basic web test, preferably in a sample plain project, and try to run it remotely. In case that execution is successful you might find a possible solution in the below listed scenarios.* 


## Unstable Tests ##

Such a problem could be caused by an unstable test. If a test is created and ran exception free on one machine it is not given that the same test will pass on the remote machine. Basically, the reason for unstable behavior could be timing problem - the test fails when the action is performed against an element that is still not present on the page. To ensure stability of the test you could use an "<a href="/features/custom-steps/execution-delay" target="_blank">execution delay</a>" or "<a href="/features/recorder/verifications/wait" target="_blank">wait for exist</a>" steps against the element that will be targeted in the next step.

## An Execution Extension is Implemented ##

The <a href="/advanced-topics/coded-samples/general/execution-extensions" target="_blank">execution extension</a> library has to be available on each execution machine's *%ProgramFiles%\Telerik\Test Studio\Bin\Plugins* folder. Using such library when executing remotely has some limitations by design though. The methods related to test lists will be executed only on the machine which hosts the scheduling server responsible for the test execution in the current setup. Those methods are *OnBeforeTestListStarted()* and *OnAfterTestListCompleted()*. The rest of the methods will be executed as expected on each execution machine.


## The Project is in TFS Source Control and a Test List is Scheduled with "Get latest version of tests automatically from TFS" Enabled ##

Important note here is that both Scheduling and Execution servers require access to TFS - the Scheduling server loads the recent available test list from TFS to determine which tests to distribute to executors as part of the currently running job and loads these tests. On the other hand the Execution server requires the access to obtain the latest checked in test files since the local project copy may not be the recent one from TFS. 

An issue might appear if the required class library files for Test Studio to communicate to TFS do not persist on the Scheduling or Execution machines. They will be automatically installed with the installation of Team Explorer 2013 (free download from an active MSDN account) or Visual Studio 2013 or earlier. 

**Note:** This library dependence problem is resolved in the product version 2017.2.824 or later.

## One of the Tests in the Test List Has Very Long Name ##

This issue could appear in a local run as well. The name of a test file is interpreted along with its full path location on disk. Windows OS limits that string up to 260 symbols so if it gets longer it cannot be resolved and used. 

Even if a local execution is possible a remote one could fail due to that limitation. The reason behind is that the project files are copied to a temporary folder on the Execution machine. In general this temp folder’s name contains the job ID which is a sequence of letters and numbers added to the file’s full path and increase its length significantly.  To avoid that scenario keep your local project on a default location on your drive and keep the test names steady and short. 

**Note:** If the issue is at least once encountered there might be corrupted values stored in the MongoDB storage. To get rid of these the DB collections should be maintained accordingly -  with the help of <a href=https://robomongo.org/download target="_blank">Robomongo</a> the corrupted test list could be located and deleted or alternatively the whole test list collection could be dropped. 

## Getting Compilation Exceptions ##

The most probable reason for the misbehavior in such scenario could be the cross test elements' definitions. Further details on the topic could be found <a     href="/troubleshooting-guide/scheduling-issues-tg/compilation-exceptions-when-execute-remotely" target="_blank">here</a> along with possible solutions.

If there are other elements missing during the compilation process - check the <a href="/features/coded-steps/add-assembly-reference" target="_blank">referred</a> to the project dlls. If there are external dll not referred from the project location it would not be transferred to the remote machine automatically. Possible workaround could be to place the external dll file on the same location as on the project host machine.