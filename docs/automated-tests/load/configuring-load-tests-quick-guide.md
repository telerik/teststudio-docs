---
title: Quick Guide on Configuring Load Tests for Web Applications in Test Studio
description: Learn how to adjust your load tests for web applications by removing unnecessary requests, adding dynamic targets, and configuring think times in Test Studio.
type: how-to
page_title: How to Set Up Load Testing for Web Applications Using Test Studio
slug: configuring-load-tests-web-apps-test-studio
tags: test studio, load testing, web applications, dynamic targets, user profile
res_type: kb
ticketid: 1622015
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
1. Create the user profile based on an existing web test. Refer to the official documentation on [adding user profiles](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/adding-user-profiles#capturing-traffic).
2. Remove requests that load visual resources (e.g., JS scripts, CSS, images) from the user profile, as the load test does not interact with the application UI.

### Dynamic Targets
3. Identify and add dynamic targets to parameterize the captured traffic, ensuring each virtual user initiates a valid user session. This involves identifying dynamic identifiers such as cookies, headers, or query parameters used in authentication and subsequent requests.
4. Review the [Page Specific Metrics view](https://docs.telerik.com/teststudio/automated-tests/load/load-testing-results/analyzing-results#page-specific-metrics-results) to analyze HTTP response codes and adjust dynamic targets accordingly.
5. For detailed guidance on identifying and adding dynamic targets, see the blog post on [custom dynamic targets in load tests](https://www.telerik.com/blogs/custom-dynamic-targets-in-load-tests).

### Additional Settings
6. Add think times to simulate real user behavior, such as delays between page loads and actions. Modify these settings as detailed in the [modifying tests section](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/modifying-tests#addremovechange-the-think-times).

### Running the Load Test
7. Initially, run the test with 1 user for 1 minute to ensure the profile is correctly set up. Once confirmed, increase the number of users as needed.
8. Follow the [best practices](https://docs.telerik.com/teststudio/automated-tests/load/running-load-test/best-practices) for running load tests.

### Additional Resources
- [Test Studio Step-by-Step: Load Testing](https://www.telerik.com/blogs/test-studio-step-by-step-load-testing)
- [Start Load Testing. Now. Really.](https://www.telerik.com/blogs/start-load-testing-now-really)
- [Designing Load Tests with Test Studio and Fiddler Everywhere in 6 Easy Steps](https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps)

## See Also
- [Getting Started with Load Testing in Test Studio](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/getting-started)
- [Analyzing Load Test Results in Test Studio](https://docs.telerik.com/teststudio/automated-tests/load/load-testing-results/analyzing-results)
- [Dynamic Targets in Load Tests](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/dynamic-targets)
- [Modifying Tests to Add Think Times](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/modifying-tests)
