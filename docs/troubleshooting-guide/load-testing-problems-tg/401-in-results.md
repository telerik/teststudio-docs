---
title: 401 in Load Test Results
page_title: 401 in Load Test Results
description: "Test Studio load test executes all requests from user profile, but these return status 401 Unauthorized Access or other error codes."
position: 1
publish: true
---
# How to Address Error 401 in Load Test Results

## PROBLEM

When running a load test, the results include a number of 401 responses.

## SOLUTION

This behavior occurs when the traffic recorded in the User Profile of the load test is not setup correctly. Thus the traffic sent towards the application server is not authorized to access it. 

The approach for addressing these errors is to revise all requests in the User Profile, remove the unnecessary queries and parameterize the dynamic parts of the rest. Use the recommended steps in <a href="/troubleshooting-guide/load-testing-problems-tg/resolving-server-load-mismatch-telerik-load-tests" target="_blank">this KB article about adjusting the user profile in Test Studio load test</a>. 

