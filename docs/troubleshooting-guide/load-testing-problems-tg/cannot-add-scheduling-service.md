---
title: Can't Add Scheduling Service
page_title: Can't Add Scheduling Service
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Cannot Add Scheduling Service

## PROBLEM

 In the **Manage Virtual Users** dialog, the **Add Scheduling Service** button does not connect to a remote scheduling service.

![Could not connect][1]

## SOLUTION

As of 2013.1.806, the Add Scheduling Service dialog only looks for Scheduling Servers that are listening on port 8009. If your scheduling service is listening on a different port, you will need to change it to 8009 before you can add it to the load test. 

[1]: /img/troubleshooting-guide/load-testing-problems-tg/cannot-add-scheduling-service/fig1.png

