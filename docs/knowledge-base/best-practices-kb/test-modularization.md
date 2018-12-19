---
title: Test Modularization
page_title: Test Modularization
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Test Modularization#

*How can I create common global functions for all my tests? Does Test Studio support global project variables or a built-in data store that can be used for all tests? Is there an ability to collaborate between tests, pass arguments to them, and run a set of tests without using test lists?*

##Solution##

The term "*Test Modularization*" is often used to describe common approaches how to configure your project to ease its maintenance and perception. Test Studio offers lots of features to obtain great project visibility and implementing their usage is  very much encouraged. There are two main approaches to accomplish good modularization: **Test as Step** and **Using Code**.

###Test as Step###

<a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a> is the method most commonly used.  The idea is to divide your script into sub-tests that could be called by a parent test. A good example for such sub-tests are "Login" and "Logout". Basically you could insert any repeating actions into a sub-test and call it whenever required. We do not limit how deep you can go with sub-tests, although it becomes unmanageable and we do not recommend to go too deep. 
 
In the <a href="/features/project-explorer/overview" target="_blank">project explorer</a> you could create sub-folders within the test project folder to better organize and group the main tests and sub-tests together. Right click the project node and select **Create Folder** to add a new one. 

###Using Code###

In this approach you use the <a href="/features/custom-steps/script-step" target="_blank">Script Step</a> feature to call your own coded functions. These coded functions can exist in any of the below places:

1. Within the same code file that test is using (each test may have one code file associated with it).

2. Within your own code file. Any code file that is placed in the project folder will automatically be included in the compile process. Thus any coded step can refer to the class (or classes) defined with this file. You can even have multiple code files of your own creation. However, you must write them using some tool outside of Test Studio, like Notepad, Visual Studio, etc.

3. Within a third party .dll. You can <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to an external .dll, either created by you or from a third party vendor, then call the functions contained in that .dll from the coded step.

4. Within a <a href="/features/coded-steps/standalone-code-file" target="_blank">standalone code file</a> which will be globally accessible in the terms of the current project. 

###Other useful features###

The closest built-in feature we have for globally accessible data is <a href="/features/data-driven-testing/Overview" target="_blank">Data Driven Testing</a>. Setting the sub-test to <a href="/features/data-driven-testing/multi-level-tests" target="_blank">Inherit the Data</a> from the parent test will allow you to have global project data. This parameterizes the sub-test by binding the parent test to a different set of data. In general you could data bind each test with separate data sources - it depends on your particular scenario. For your convenience there are different <a href="/features/data-driven-testing/add-data-source" target="_blank">internal and external sources</a> supported. 
 
Available in Test Studio as well is the implemented <a href="/features/recorder/verifications/extraction" target="_blank">Extraction step</a> which stores the value of an element into a variable which could be passed for data binding. The above approach could be obtained in code as well - define your global variables in code and use them in your code file. You also have the option to <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Get and Set the Value of a Variable in code</a> and pass it to a non coded step similar to the Extraction step. 

The opportunities that data driven testing offers do not end here - the <a href="/features/logical-steps/loop" target="_blank">find logic of an element could be also bound</a> to the extracted variables or the data source. 

Test Studio offers other useful features implemented in its UI that could help for modulirizing a test project properly. Namely these are the logical steps <a href="/features/logical-steps/if-else" target="_blank">if...else</a>, <a href="/features/logical-steps/loop" target="_blank">loop</a> and <a href="/features/logical-steps/while-loop" target="_blank">while...loop</a>. Combining these steps with a <a href="/features/data-driven-testing/attach-columns-verifications" target="_blank">data bound verification</a> could bring your tests to another level of automation. 

All of the above allow you to create a single test/project that could be automatically adjusted for each execution/iteration and offers good visibility into a project to ease its maintenance.     

