---
title: Bind the Data Source Columns to Test Steps
page_title: Bind the Data Source Columns to Test Steps
description: "How to set the values from the data source to be used in the test steps in Test Studio. Set a column from the data source/excel/csv/database for a enter text step in Test Studio. Parameterize the test in Test Studio. Parameterize the values selected from a drop down/ the values entered in a form"

position: 5
---
# Attach Data Source Columns to Test Steps

Recording a test scenario allows you to interact with different controls on the page. Depending on these and the action performed against them various steps get recorded in Test Studio test. Most action and verification steps have at least one property, that can be bound to a column from your data source.

Once you have <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">bound a test to a data source</a>, you are ready to continue with binding the recorded steps.
Use the `Step Properties` pane to find out which properties can be data driven for a particular step.

## Choose a Step Property to Data Bind

Choose an _action_ or _verification_ step from the recorded steps in a test and expand it with double-click.

![expand-step](/img/automated-tests/data-drive-test/local-data-driven-test/expand-step.png)

Use the `Data Bind` button to open the `Data binding` dialog. It lists all step's fields which you can use for binding. 

![data-bind-dialog](/img/automated-tests/data-drive-test/local-data-driven-test/data-bind-dialog.png)

The `Data binding` dialog can be also opened through the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a>. The `Bindings` property is the first in the list. Click the three dots button at its right side to open the `Data binding` dialog.

![open-step-properties](/img/features/data-driven-testing/attach-columns-input-values/open-step-properties.png)

> __Note__
><br>
><br>
> Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the `Properties pane` can be on different location within your project.

Some steps allow you to bind more than one property. In such case the `Data binding` dialog lists all available fields to data drive.

![bindings-dropdown](/img/features/data-driven-testing/attach-columns-input-values/bindings-dropdown.png)

## Data Bind a Step Property

Once you know which step property you need to bind and have attached the required data source, you can select the corresponding column from the attached data. Each property available for binding is associated with a drop-down list where you can find the list of all columns from data source. Choose the column which holds the data for this step field. 

![data-columns-dropdown](/img/features/data-driven-testing/attach-columns-input-values/data-columns-dropdown.png)

Click the `OK` button to confirm the selection and close the `Data binding` dialog.

## Use an Extracted Variable to Data Bind a Test Step

If the test scenario requires some dynamically generated data to be used in the upcoming steps, you can use <a href="/features/recorder/verifications/extraction" target="_blank">the option to extract the value of an element during the test run to a "run-time" variable</a> and bind that variable to any property from the upcoming steps.

![bind-extracted-variable](/img/features/data-driven-testing/attach-columns-input-values/bind-extracted-variable.png)

## Use Data Columns Not Directly Bound to the Test

Test Studio allows you to use data, which is not directly referenced in the test. This could be <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">an extracted variable generated in a coded step</a>, or this test is used as step in another test and is <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">set to use the data source of the "parent" test</a>.

For these cases you will need to manually enter the name of the extracted variable, or the parent data source column, which the step property need to access. Open the `Data binding` dialog and the dropdown of the property to bind. Type the external variable name in the _`Add coded data variable`_ text field. Then, click the curly brackets in front of the text field.

![external-variable](/img/features/data-driven-testing/attach-columns-input-values/external-variable.png)

Click the `OK` button to confirm the selection and close the `Data binding` dialog.

