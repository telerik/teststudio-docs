---
title: Multi-level Tests
page_title: Multi-level Tests
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/data-driven-testing/multi-level-tests.aspx, /user-guide/data-driven-testing/multi-level-tests
position: 6
---
# Multi-level Tests


We have covered how a single level test behaves. Suppose you have more than one level using the ["Test as Step"](/features/custom-steps/test-as-step) feature? What happens? This is where Test Studio can be both complex and powerful. Here are some possible combinations and their behavior:

## Data bound Test A calls Test B

In this scenario, the data source definition for Test A will propagate down to Test B and be available for use by Test B. This is useful if you want to have one large data source supplying data to all the tests in a chain. Test A will run X times calling Test B for each iteration.

 
Example

- Test B is a Test as Step within Test A
- Data is attached to Test A.
- Test B is bound to columns from Test A's data for text entry and/or verification purposes.
 

> Test B references the data from Test A without having its own data source. The **InheritParentDataSource** [Test Property](/features/test-maintenance/test-properties-standalone) for Test B is set to True.

##Test A calls data bound Test B

In this scenario, Test A will execute only once. It will call Test B (as a Test as Step) which will execute X times as defined by the data source. This is useful if you want Test A to perform an operation once (a login for example), then execute a sequence of data driven tests.

Example

- Test A has 3 steps: login, Test as Step (Test B), and logout.
- Test B performs a data driven text input, search, and verification.


> Test B is data bound, Test A is not.

##Data bound Test A calls data bound Test B

In this scenario, Test A will execute X times according to the number of rows in its data source and call Test B X times. Test B will in turn execute Y times according to number of rows in its data source before returning to Test A. In the end, Test B will execute a total of X * Y times. This is useful if you want to perform the same data driven test in different environments (alternate login IDs, for example).

Example

- Same as second example above, except Test A is also data bound to allow for multiple logins with different usernames and passwords.

 

> Both Tests are data bound. Test A is bound with usernames and passwords, Test B is bound with search queries.