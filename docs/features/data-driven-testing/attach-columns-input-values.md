---
title: Attach Columns to Input Values
page_title: Attach Columns to Input Values
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/data-driven-testing/attach-columns-to-input-values.aspx, /user-guide/data-driven-testing/attach-columns-to-input-values
position: 4
---
# Attach Columns to Input Values

Most action steps have at least one property that can be bound to a column from your data source. To bind a test step property to a project data source:

1.&nbsp; Click the step in the Test Steps pane.

2.&nbsp; Click ![...][1] next to the (Bindings) Property.

3.&nbsp; Click the drop-down menu next to the test step property.

![drop down][2]

4.&nbsp; Select a column name from the Value drop-down and click **Set** button. This list will **not** include columns from the parent data source of a [test as step](/features/custom-steps/test-as-step).

![select value][3]

If you've [Set an Extracted Variable in Code](/advanced-topics/coded-samples/general/extracted-variables-in-code) or wish to access the data source of a parent test, type the variable name in the text box (without the $ notation), click the brackets and **Set** button:

![var][4]

[1]: /img/features/data-driven-testing/attach-columns-input-values/fig1.png
[2]: /img/features/data-driven-testing/attach-columns-input-values/fig2.png
[3]: /img/features/data-driven-testing/attach-columns-input-values/fig3.png
[4]: /img/features/data-driven-testing/attach-columns-input-values/fig4.png