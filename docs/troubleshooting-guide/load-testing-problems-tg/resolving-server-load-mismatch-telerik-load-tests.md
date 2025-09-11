---
title: Resolving Mismatch in Server Load During Telerik Test Studio Load Tests
description: Troubleshooting server load mismatch during load tests in Telerik Test Studio, identifying dynamic targets, and adjusting settings for accurate simulation.
type: how-to
page_title: Fixing Server Traffic Discrepancy in Telerik Test Studio Load Tests
meta_title: Fixing Server Traffic Discrepancy in Telerik Test Studio Load Tests
slug: resolving-server-load-mismatch-telerik-load-tests
tags: telerik test studio, load tests, dynamic targets, test studio settings, troubleshooting
res_type: kb
ticketid: 1683582
---


## Description

I designed a load test in Telerik Test Studio to simulate up to 10,000 users, but the server only receives a fraction of the intended traffic. Requests per second do not match the test design, even though CPU and memory usage on both the site server and the hosting virtual machine have sufficient capacity. I need to troubleshoot why the traffic isn't being generated correctly.

This knowledge base article also answers the following questions:
- How do I fix low server traffic during load tests in Telerik Test Studio?
- How do I adjust user profiles and dynamic targets in Telerik Test Studio load tests?
- How can I simulate accurate server load with multiple concurrent users in Test Studio?

## Solution

To ensure proper load simulation and address the discrepancy in server traffic, follow these steps:

### Adjusting the User Profile

1. Open the user profile created for the load test. This profile is based on the HTTP(S) traffic captured during web test execution.
2. Remove requests for visual resources such as JavaScript scripts, CSS files, images, fonts, and icons. These requests are unnecessary for load testing since the test doesn't use the application UI.
3. Retain only essential requests required for interactions with the application server.

### Configuring Dynamic Targets

1. Identify dynamic session identifiers, such as cookies, headers, or query parameters, exchanged during web test execution. These identifiers ensure valid user sessions during the load test.
2. Add dynamic targets to replace these identifiers for each virtual user:
   - Use the [source step properties](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/dynamic-targets#source-section-properties) to define the part of the response (e.g., body, headers, cookies).
   - Use the [search options](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/dynamic-targets#search-options) to pinpoint specific dynamic values.
   - Set up the [destination step properties](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/dynamic-targets#destination-section-properties) to reuse the dynamic value (e.g., as a header, query parameter, or cookie).
3. Refer to this [blog post about dynamic targets](https://www.telerik.com/blogs/custom-dynamic-targets-in-load-tests) for a detailed example of setting up a Request Verification token.

### Adding Think Times

1. Include [think times](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/modifying-tests#addremovechange-the-think-times) in the user profile to simulate realistic user behavior. Users typically wait before interacting with the application, and these think times ensure accurate behavior simulation.

### Running the Load Test

1. Run the test with 1 virtual user for 1 minute to verify the setup and ensure all requests execute successfully.
2. Once verified, increase the number of virtual users and test duration to simulate the desired load.
3. Use [remote execution](https://docs.telerik.com/teststudio/automated-tests/load/running-load-test/best-practices) to simulate high user concurrency effectively.

### Additional Resources

- [Getting Started with Load Testing in Test Studio](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/getting-started)
- [Best Practices for Running Load Tests](https://docs.telerik.com/teststudio/automated-tests/load/running-load-test/best-practices)
- [Step-by-Step: Load Testing](https://www.telerik.com/blogs/test-studio-step-by-step-load-testing)
- [Designing Load Tests with Test Studio and Fiddler Everywhere in 6 Easy Steps](https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps)

## See Also

- [Dynamic Targets Overview](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/dynamic-targets)
- [Load Test Settings](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/test-settings)
- [Modifying User Profiles in Load Tests](https://docs.telerik.com/teststudio/automated-tests/load/designing-load-tests/modifying-tests) 
