---
title: Load Test Run Quits
page_title: Load Test Run Quits
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Load Test Run Quits


##PROBLEM

Load test execution does not complete successfully. 

##SOLUTION

This behavior may be caused by a 'File name too long' exception. This is because the load test project location file path length exceeds 255 characters. To address this, relocate or rename the load project files and folders to avoid exceeding the 255 character limit.
