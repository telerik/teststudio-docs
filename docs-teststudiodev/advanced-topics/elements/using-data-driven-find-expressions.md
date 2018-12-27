---
title: Data Driven Find Expression
page_title: Data Driven Find Expression
description: Use a data source values in how an element is located. 
position: 1
---
# Data-driven find logic

<a name="data-driven"></a>Here, you can also <a href="/features/data-driven-testing/overview" target="_blank">data drive</a> the element find expression. If your test has an attached data source, the value fields of the find expressions for your elements will include a drop-down list displaying columns from your data source.

![Data drive find exp](images/using-data-driven-find-expressions/fig14.png)

Selecting a column binds the data value to the find expression rule.

![Data drive find exp](images/using-data-driven-find-expressions/fig15.png)

If the element was not found, click the **Troubleshoot** button. Choose a suggested fix from the Troubleshoot screen.

![Troubleshoot](images/using-data-driven-find-expressions/fig16.png)

There are three additional buttons in the upper right of the **Find Element** dialog:

![Additional Buttons](images/using-data-driven-find-expressions/fig17.png)

- **Select New Element** - choose this option if the incorrect element was selected for this step. This will clear your current settings and <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> provides new filters for the new element. 

![Select New Element](images/using-data-driven-find-expressions/fig18.png)

- **Advanced** - edit the Find Settings using a string-based expression builder. 

![Advanced](images/using-data-driven-find-expressions/fig19.png)

- **Reset** - restores fields to their original settings. 

![Reset](images/using-data-driven-find-expressions/fig20.png)

Once you've confirmed you are targeting the correct element and it is correctly found, click Save and Close. If the modified element is used by multiple automation steps, you are prompted to select the steps you want to persist changes to.

![Test Case Selector](images/using-data-driven-find-expressions/fig21.png)
