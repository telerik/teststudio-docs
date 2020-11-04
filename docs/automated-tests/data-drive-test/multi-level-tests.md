---
title: Multi-Level Data Driven Tests
page_title: Multi-Level Data Driven Tests
description: "What is the execution flow in Test Studio test for nested data driven tests. I have a test step bound to a data source, which does not use it, but the parent test source instead. Data driven/bound test is nested under a test. Data driven/bound test is nested under a data driven/bound test. A test is nested under a data driven/bound test. Data Driven Tests Used as Step in another test"
position: 6
---
# Data Driven Tests Used as Step

We have covered how a single level test behaves. But what if there are __tests nested as steps within a data driven test__? Or if a __data driven test is used as step in another test__?

One of the great features of Test Studio is that you __can reuse common <a href="/features/custom-steps/test-as-step" target="_blank">tests as steps</a>__ in other more complex test scenarios. When this is combined with the data driven testing approach, Test Studio becomes both complex and powerful.

And to make this even more exciting, a __nested test in Test Studio can use the data source bound to its parent test__ without having its own.

In this article you can find the possible combinations for data driven and nested tests and what to expect from their execution flow.

> __Note__
><br>
><br>
> Each test in Test Studio can use a <a href="/features/test-maintenance/test-properties-standalone" target="_blank">__test property__</a> called ___'InheritParentDataSource'___. Once this is set to true, __all data bound steps in the child test will take the data from the parent test's data source__.
><br>
> Thus, if there is no column with that name or the parent test has no data source, the nested test will fail to find the binding details.

## Data Bound Test A Calls Test B

This combination can be considered as the baseline because the execution outcome is similar to the results generated in the <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">end-to-end scenario using the built-in data table</a>. The only difference is that one of the steps is a test.

In this scenario, the __data source definition for Test A will propagate down to Test B__ and will be available for use by Test B, if the ___InheritParentDataSource_ property is enabled__ for the nested test. This is useful, if you want to have one large data source, supplying data to all the tests in a chain.

For this execution __Test A will run X times (the number of iterations) calling Test B for each iteration__. If Test B uses the data parent data source, it will have access to the current iteration value.

__Example:__

- Data source is attached to Test A.
- Test A has three rows in the data source, which results in three iterations.
- Test A has data bound steps.
- Test B is called as step within Test A.
- Test B uses __InheritParentDataSource__ set to true.
- Test B is bound to columns from Test A's data for text entry and/or verification purposes.

__Execution Outcome:__

Test A will be executed three times. For each iteration in Test A, Test B will be executed as step once and will use the values for the current iteration from Test A.

## Test A Calls Data Bound Test B

In this scenario, Test A will execute only once. It will call Test B (as a test as step), which will execute X times as defined by the data source. This is useful if you want Test A to perform an operation once (a login for example), then execute a sequence of data driven tests.

__Example:__

- Test A has 3 steps: login, Test as Step (Test B), and logout.
- Test A is not using data bound steps.
- Data source is attached to Test B.
- Test B has three rows in the data source, which results in three iterations.
- Test B performs text input to search a product, and verification.
- Test B actions are data bound to its own data source.

__Execution Outcome:__

Test A will be executed once. When the test run gets to the test as step Test B, this will be executed three times in a row (defined by its data source), and then the test will proceed to the next step in Test A.

## Data Bound Test A Calls Data Bound Test B

In this scenario, Test A will execute X times according to the number of rows in its data source and call Test B X times. Test B will in turn execute Y times according to number of rows in its data source before returning to Test A. In the end, Test B will execute a total of X * Y times. This is useful if you want to perform the same data driven test in different environments (alternate login IDs, for example).

__Example:__

Same as second example above, except Test A is also data bound to allow for multiple logins with different usernames and passwords.

- Test A has 3 steps: login, Test as Step (Test B), and logout.
- Data source is attached to Test A.
- Test A has three rows in the data source, which results in three iterations.
- Test A has data bound steps.
- Data source is attached to Test B.
- Test B has two rows in the data source, which results in two iterations.
- Test B performs text input to search a product, and verification.
- Test B uses __InheritParentDataSource__ set to false.
- Test B actions are data bound to its own data source.

__Execution Outcome:__

Test A will be executed three times. For each iteration in Test A, Test B will be executed as step with the number of iterations defined in its own data source - twice, for this example. Then, Test A will proceed to its next step, and then iteration. That said, Test B will be executed twice for each of the three alternate logins in Test A - altogether six times for the overall Test A run.