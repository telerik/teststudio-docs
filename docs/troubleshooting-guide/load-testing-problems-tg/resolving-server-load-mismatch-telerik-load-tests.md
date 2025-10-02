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

# How to Address Mismatch in Server Load During Load Test Runs

## Description

I designed a load test in Telerik Test Studio to simulate multiple users, but the server only receives a fraction of the intended traffic. Requests per second do not match the test design, even though CPU and memory usage on both the site server and the hosting virtual machine have sufficient capacity. I need to troubleshoot why the traffic isn't being generated correctly.

This knowledge base article also answers the following questions:
- How do I fix low server traffic during load tests in Telerik Test Studio?
- How do I adjust user profiles and dynamic targets in Telerik Test Studio load tests?
- How can I simulate accurate server load with multiple concurrent users in Test Studio?

## Solution

To ensure proper load simulation and address the discrepancy in server traffic, you need to adjust the load test user profile to handle all requests correctly. Follow each of these steps for this: 

<!-- no toc -->
- [Adjusting the User Profile](#adjusting-the-user-profile)
- [Configuring Dynamic Targets](#configuring-dynamic-targets)
- [Adding Think Times](#adding-think-times)
- [Running the Load Test](#running-the-load-test)
- [Additional Resources](#additional-resources)

> __Note!__ 
> <br>
> All images listed in the article are for illustrative purposes and do not reflect any real life scenario. The adjustments to perform are specific for the captured traffic in each user profile.

### Adjusting the User Profile

1. Open the user profile created for the load test in Edit mode (double click the profile to work with it). This profile is based on the HTTP(S) traffic captured during the execution of the base web test scenario used to generate the user profile.
   
   ![Open Load test user profile](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/edit-profile.gif)

2. Remove requests for visual resources such as JavaScript scripts, CSS files, images, fonts, and icons. These requests are unnecessary for load testing since load test doesn't use the application UI.

   ![Example of requests loading visual resources](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/requests-loading-visual-resources.png)

3. Retain only essential requests required for the actual interactions with the application server.

   ![Example of non-essential requests from 3rd party services](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/remove-queries-to-3rd-party-services.png)

### Configuring Dynamic Targets

1. Review the captured traffic which remains after clearing the non-essential requests and drill down which are the dynamic session identifiers - such as cookies, headers, or query parameters - exchanged during the web test execution. These identifiers ensure the user session is accepted from the application server as a valid one so they need to be correctly handled during the load test execution. 

   <table id="no-table">
   <tr>
   <td>![Dynamic value in response](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/identify-dynamics-in-response.png)<br>**Dynamic value returned in response**</td>
   <td>![Reused dynamic value in next request](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/identify-dynamics-in-request.png)<br>**Reused dynamic value in next request**</td>
   <tr>
   <table>
   
2. Add dynamic targets to replace these identifiers for each virtual user:
   
   - Use the <a href="/automated-tests/load/designing-load-tests/dynamic-targets#source-section-properties" target="_blank">source step properties</a> to define the part of the response (e.g., body, headers, cookies).
   - Use the <a href="/automated-tests/load/designing-load-tests/dynamic-targets#search-options" target="_blank">search options</a> to pinpoint specific dynamic values.
   - Set up the <a href="/automated-tests/load/designing-load-tests/dynamic-targets#destination-section-properties" target="_blank">destination step properties</a> to reuse the dynamic value (e.g., as a header, query parameter, or cookie).

   > __Tip__
   ><br>
   > The example shows setting a dynamic target to cover a redirect to a specific URL generated during the current user session. 

   ![Create custom dynamic target to cover the URL redirect](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/add-dynamic-target.png)

   - After adding the custom dynamic target you can see it listed in the target step request field.  

   ![See the custom added dynamic target listed in the target step request part](/img/troubleshooting-guide/load-testing-problems-tg/resolve-server-load-mismatch/see-added-dynamic-target-in-target-step.png)

3. Refer to this <a href="https://www.telerik.com/blogs/custom-dynamic-targets-in-load-tests" target="_blank">blog post about dynamic targets</a> for another detailed example of setting up a Request Verification token.
4. Iterate through all requests in the captured traffic to identify all necessary dynamic targets. Usually in real life scenario more than one dynamic identifier needs to be transferred from one step's response to the following requests.
   - __E.g.__: 
   - A session identifier cookie returned in one request's response is then used in all following requests. So you need a dynamic target for each step. 
   - Or, in one request's response you find a session identifier cookie and a verification token which are reused in the next step - these two need separate dynamic targets from one step to the other. 

### Adding Think Times

Include <a href="/automated-tests/load/designing-load-tests/modifying-tests#addremovechange-the-think-times" target="_blank">think times</a> in the user profile to simulate realistic user behavior. 

Users typically need time to process the displayed information before interacting with the application, and the think times simulate delays between requests in your User Profile. That way executing the load test ensures accurate user behavior simulation.

### Running the Load Test

1. <a href="/automated-tests/load/designing-load-tests/test-settings#available-users-and-time-settings" target="_blank">Set the test to run</a> with 1 virtual user for 1 minute to verify the setup and ensure all requests execute successfully.
2. Once verified, increase the number of virtual users and test duration to simulate the desired load.
3. When the User profile is validated and you are sure it covers the user workflow, you can use <a href="/automated-tests/load/running-load-test/best-practices" target="_blank">remote execution</a> to simulate high user concurrency effectively.

### Additional Resources

- [Getting Started with Load Testing in Test Studio](/automated-tests/load/designing-load-tests/getting-started)
- [Dynamic Targets Overview](/automated-tests/load/designing-load-tests/dynamic-targets)
- [Load Test Settings](/automated-tests/load/designing-load-tests/test-settings)
- [Modifying User Profiles in Load Tests](/automated-tests/load/designing-load-tests/modifying-tests)
- [Best Practices for Running Load Tests](/automated-tests/load/running-load-test/best-practices)
- [Step-by-Step: Load Testing](https://www.telerik.com/blogs/test-studio-step-by-step-load-testing)
- [Designing Load Tests with Test Studio and Fiddler Everywhere in 6 Easy Steps](https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps)

## See Also

- [Dynamic Targets Overview](/automated-tests/load/designing-load-tests/dynamic-targets)
- [Load Test Settings](/automated-tests/load/designing-load-tests/test-settings)
- [Modifying User Profiles in Load Tests](/automated-tests/load/designing-load-tests/modifying-tests) 
