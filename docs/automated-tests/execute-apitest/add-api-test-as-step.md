---
title: Add API Test as Step
page_title: Add API Test as Step
description: "Insert an API Test Studio test within a web test execution. Add an API test as step in a Test Studio web test"
position: 0
---
# Add API Test as Step

The implemented integration between __Test Studio Web&Desktop__ and __Test Studio for APIs__ projects allows you to insert an API test and execute it as a step in a web test.

## Add an API Test as Step

To add a new API test as step first create a web test. Then the option is available in the Step Builder among the steps in the Common section.

![Api Test as step](/img/features/execute-apitest/add-api-test-as-step/add-step.png)

Double click it to trigger the ___'Select API test'___ dialog.

![Select API test window](/img/features/execute-apitest/add-api-test-as-step/select-apitest-window.png)

The available options are either to create a new test or import an existing one.

<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
		<td>

<img src="/img/features/execute-apitest/add-api-test-as-step/create-edit.png" alt="Create an API Test" /></td>
<td>
		
<img src="/img/features/execute-apitest/add-api-test-as-step/import-existing.png" alt="Add existing API test" /></td>
</tr>
</table>

## Create Test

___'Create Test'___ creates and opens an empty API project which is nested in the Test Studio project's root folder. The integrated project allows you to <a href="https://docs.telerik.com/teststudio-apis/features/steps/overview" target="_blank">create new API tests</a>.

## Import Existing Test

___'Import Existing Test'___ allows you to browse your files and add an already designed API test ready for execution. The imported API test will be inserted in the nested API project if one already exists or will create a new one containing the added test.

![Browse API test](/img/features/execute-apitest/add-api-test-as-step/browse-apitest.png)

Once a test file is selected a warning message appears that <a href="/features/execute-apitest/edit-integrated-api-project" target="_blank">any external dependencies need to be added manually</a>.

![External dependencies](/img/features/execute-apitest/add-api-test-as-step/warning.png)

Once the test is imported click on it and then the _Select_ button. If there are multiple API tests in the nested project they all will be listed in this view and available for execution as step in a web test.

![Select a test to add in step](/img/features/execute-apitest/add-api-test-as-step/select-test.png)

## See Also

* <a href="https://www.telerik.com/blogs/power-up-your-ui-tests-with-api-test-as-step-in-telerik-test-studio" target="_blank">Power Up Your UI Tests with 'API Test as Step' in Telerik Test Studio</a>.

