---
title: Passing Variables Between API and Web&Desktop Projects
page_title: Passing Variables Between API and Web&Desktop Projects
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
# Passing Variables Between API and Web&Desktop Projects

When an API test is executed as a step in a Web&Desktop test, we often need to get a value that is acquired from a http response in the API test and use it in the Web&Desktop test or vice versa. To do that, all you need to do is to extract it into a variable. Any variable extracted in the API test by a Set Variable Step becomes available in the context of the Web&Desktop test and any variable extracted in the Web&Desktop test can be set as project level variable for an API test.

## Passing a Variable Generated from an API Test

>The variables generated from the API test execution which could be passed back to the web test are only these set in a <a href="https://docs.telerik.com/teststudio-apis/features/steps/set-variable" target="_blank">Set Varaible Step</a>.

Since the variable is not defined in Test Studio UI it is treated as it is a varaible extracted in code. Simply type the variable name in the text box (without the $ notation), click on the brackets and then on the _Set_ button to apply the changes.

![Use variable from API test in a web test][1]

## Passing a Variable Generated from a Web Test

Each _Execute API test_ step has an additional <a href="/features/test-maintenance/test-step-properties" target="_blank">property</a> named _Variables_.

![Variables property][2]

Click on the down arrow to expand the Variables pane. Use the _Add_ button to set a new variable using an extracted value from the web test.

![Varianle pane][3]

Define the variable with a name and value.

* What is listed in the ___Name___ field will be used in the API project to <a href="https://docs.telerik.com/teststudio-apis/features/variables#Referencing-Variables" target="_blank"> reference the variable</a>.
* The ___Value___ field determines which extracted variable from the web test to be used. As it will be used in the API project the value can be passed using the API testing convention using __double curly brackets__ - {%raw%}{{extracted-from-web-test-variable-name}}{%endraw%}.

![Add Varianle][4]

> The variable defined and set from a web test will be set as a __project level__ variable in the API project.

[1]: /img/features/execute-apitest/passing-variables/use-variable-in-web-test.png
[2]: /img/features/execute-apitest/passing-variables/variables-property.png
[3]: /img/features/execute-apitest/passing-variables/variable-pane.png
[4]: /img/features/execute-apitest/passing-variables/add-variable.png
