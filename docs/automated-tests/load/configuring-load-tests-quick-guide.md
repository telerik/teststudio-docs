---
title: Quick Guide on Configuring Load Tests for Web Applications in Test Studio
description: Learn how to adjust your load tests for web applications by removing unnecessary requests, adding dynamic targets, and configuring think times in Test Studio.
type: how-to
page_title: How to Set Up Load Testing for Web Applications Using Test Studio
slug: configuring-load-tests-web-apps-test-studio
tags: test studio, load testing, web applications, dynamic targets, user profile
res_type: kb
ticketid: 1622015
position: 0
---

## Description

When attempting to perform load testing on a web application, the process entails more than just recording and replaying a web test. It involves meticulous adjustments to ensure only essential requests are included, dynamic identifiers are properly handled, and user behavior is realistically simulated. 

This KB article also answers the following questions:
- How do I remove unnecessary requests from my load test in Test Studio?
- What are dynamic targets in Test Studio and how do I use them?
- How do I simulate real user behavior in load testing with Test Studio?

## Solution
To set up a load test for a web application in Test Studio, follow these steps:

### User Profile in Load Test

1. Start by [creating a user profile](/automated-tests/load/designing-load-tests/adding-user-profiles#add-a-user-profile). This will capture the HTTP(S) requests generated during the web test scenario.

2. Review the captured traffic and remove requests that load visual resources (e.g., JS scripts, CSS, images) from the user profile. Load test does not interact with the application UI so this type of requests are not needed.

### Managing Dynamic Targets

3. Dynamic targets allow parameterization of captured traffic. This is essential for each virtual user to initiate a valid user session recognized by the server.

4. Identify dynamic targets based on the captured traffic, ensuring each virtual user initiates a valid user session throughout the complete user profile. This involves finding the dynamic identifiers such as cookies, headers, query parameters, etc., used in authentication and subsequent requests.

5. Add dynamic targets by selecting the source step and destination step, defining how the dynamic value will be reused (e.g., as a header, query parameters, or cookie). For detailed instructions, visit the [dynamic targets documentation](/automated-tests/load/designing-load-tests/dynamic-targets#add-custom-dynamic-target).

6. For detailed guidance on identifying and adding dynamic targets, see the blog post on [custom dynamic targets in load tests](https://www.telerik.com/blogs/custom-dynamic-targets-in-load-tests).


### Additional Settings

7. Add think times to simulate real user behavior, such as delays between page loads and actions. Modify these settings as detailed in the [modifying tests section](/automated-tests/load/designing-load-tests/modifying-tests#addremovechange-the-think-times).

### Running the Load Test

8. Initially, run the test with 1 user for 1 minute to ensure the profile is correctly set up. Once confirmed, increase the number of users as needed.
   
9.  Follow the [best practices](/automated-tests/load/running-load-test/best-practices) for running load tests.

### Additional Resources
- [Test Studio Step-by-Step: Load Testing](https://www.telerik.com/blogs/test-studio-step-by-step-load-testing)
- [Start Load Testing. Now. Really.](https://www.telerik.com/blogs/start-load-testing-now-really)
- [Designing Load Tests with Test Studio and Fiddler Everywhere in 6 Easy Steps](https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps)

## See Also
- [Getting Started with Load Testing in Test Studio](/automated-tests/load/designing-load-tests/getting-started)
- [Analyzing Load Test Results in Test Studio](/automated-tests/load/load-testing-results/analyzing-results)
- [Dynamic Targets in Load Tests](/automated-tests/load/designing-load-tests/dynamic-targets)
- [Modifying Tests to Add Think Times](/automated-tests/load/designing-load-tests/modifying-tests)
