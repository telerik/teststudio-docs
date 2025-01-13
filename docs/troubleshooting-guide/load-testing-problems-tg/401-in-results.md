---
title: 401 in Results
page_title: 401 in Results
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
publish: false
---
# Error 401 in Results

## PROBLEM

When running a load test, the results include a number of 401 responses.

## SOLUTION

This behavior can occur when you configure your load test to use Windows Authentication credentials. Test Studio opens a new connection each time it executes a user profile, which can result in a large number of 401 responses containing authentication challenges applicable to the requested resource. 

- If one or two 401 responses are followed by a 200-Okay response, this means that authentication was successful. 

- If there are more than two 401 responses with no 200 response, this means that your load test is not providing valid credentials when they are required by the server. 

- If the 401 responses are followed by a 403-Forbidden response, this means that the credentials your load test provided lacked the permissions required for the requested resource.


For more information, see <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html#sec10.4.2" target="_blank">Fielding et al. (June 1999), "Hypertext Transfer Protocol – HTTP/1.1", IETF, RFC 2616, Section 10.4.2</a>.