---
title: Help file
page_title: help file
position: 1
publish: false
---


## Local data binding
open the <a href="/features/test-maintenance/test-step-properties" target="_blank">_Step Properties pane_</a>. 

1. The ___Bindings___ property is the first in the list. Click the three dots button on the right to open the step fields that you can bind to data.

    ![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

    > __Note__
    ><br>
    ><br>
    > Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can have a different location within your project.

    The _Enter text_ step allows only its ___Text___ field to be data driven and, thus, this is the only one listed.

1. Click on the drop-down next to the  ___Text___ field to expand the data source columns list. In this scenario a single column is in the list - the _`productName`_, so select this one.

    ![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

1. Click the _Set_ button to confirm the selection and close the _Properties pane_.

    ![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

    > __Tip__
    ><br>
    ><br>
    > See <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">How to bind a step to a data source column</a> for more information.

1. Apply the same sequence of steps for the wait step. We add a wait step to verify that the search action is completed successfully. Note that the field that you need to bind in the wait step properties is `TextToMatch`.

    ![wait-step-binding](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-binding.png)


## External data source binding

1. Click on the __Enter text__ step (number 3. for the current scenario) and open the <a href="/features/test-maintenance/test-step-properties" target="_blank">_Step Properties pane_</a>.

1. The ___Bindings___ property is the first in the list. Click the three dots button on the right to open the step fields that you can bind to data.

    ![enter-text-properties](/img/automated-tests/data-drive-test/local-data-driven-test/enter-text-properties.png)

    > __Note__
    ><br>
    ><br>
    > Depending on the <a href="/automated-tests/customize-project/custom-layout" target="_blank">project layout</a> you are using, the _Properties pane_ can have a different location within your project.

    The _Enter text_ step allows only its _Text_ field to be data driven and this is the only one listed.

1. Click on the drop-down next to the  ___Text___ field to expand the data source columns list. In this scenario a single column is in the list - the _`productName`_, so select this one.

    ![select-column](/img/automated-tests/data-drive-test/local-data-driven-test/select-column.png)

1. Click on the _Set_ button to confirm the selection and close the _Properties pane_.

    ![set-binding](/img/automated-tests/data-drive-test/local-data-driven-test/set-binding.png)

    > __Tip__
    ><br>
    ><br>
    > See <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">How to bind a step to a data source column</a> for more information.

1. Apply the same sequence of steps for the wait step. We add a wait step to verify that the search action is completed successfully. Note that the field that you need to bind in the wait step properties is ___`TextToMatch`___.

    ![wait-step-binding](/img/automated-tests/data-drive-test/local-data-driven-test/wait-step-binding.png)