---
title: Introduction
page_title: Introduction to Load Testing
description: "Load Testing in Test Studio. The Load Testing feature in Test Studio Standalone enables you to assess how your web applications meet business needs for availability and user satisfaction"
position: 0
---
# Introduction to Load Testing

The Load Testing feature in Test Studio Standalone enables you to assess how your web applications meet business needs for availability and user satisfaction. We make it easy for you to get started and find the data you need to help make your decisions, but we also give you the flexibility and power to create elaborate, complex load scenarios to meet your most demanding needs.

![Load Test][1]

{% if site.has_cta_panels == true %}
{% include cta-panel-introduction.html %}
{% endif %}

## What is Load Testing in Test Studio?

<a href="http://www.telerik.com/automated-testing-tools/load-testing.aspx" target="_blank">Telerik’s Test Studio Load Testing feature</a> is a set of services and tests that, when used together, will put your website under a set user load. The user load sent to the application server is defined by the specific load test being run. Using Test Studio you can measure how your website performs when put under load. Test Studio Load Testing can measure <a href="/knowledge-base/load-testing-kb/analyze-results" target="_blank">a range of useful properties</a>, including HTTP timers and <a href="/features/testing-types/load-testing/monitor-perf-metrics" target="_blank">machine performance metrics</a>.

## When Load Testing Can Help?

Load tests help answer some of the most critical questions organizations have about how their systems behave under load:

- How is a user’s experience on our site when thousands of other users are hitting it at the same time? (General load testing)
- How stable is our site when lots of users have been hitting it for days? (<a href="/knowledge-base/load-testing-kb/load-strategies#soak-testing" target="_blank">Soak testing</a>)
- How many users can our site support before it crashes? (<a href="/knowledge-base/load-testing-kb/load-strategies#stress-testing" target="_blank">Stress</a> or tipping testing)

> **<font color="red">CAUTION:</font>** 
><br>
><br>
> To perform any sort of load testing you must be in control of the website/webserver you plan to test and be prepared for the consequences that may occur as a result of running a load test. It is easy to take down a website using load testing. In fact, that's one of the purposes of load testing: to discover the breaking point of your website. Progress Test Studio's Load Testing feature has deliberately blocked Telerik.com from being used in a load test for this very reason.

## See Also

* <a href="https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps" target="_blank">Designing Load Tests with Test Studio and Fiddler Everywhere in 6 Easy Steps</a>

## First Steps with Load Testing in Test Studio

> __Tip__
><br>
><br>
> You can checkout  <a href="https://www.telerik.com/blogs/designing-load-tests-test-studio-fiddler-6-easy-steps" target="_blank">this blog post</a>, which guides you through the steps of setting up a load test.

1. <a href="/features/testing-types/load-testing/designing-tests" target="_blank">Design your load test</a>. This includes selecting agents and virtual users, capturing or importing web traffic, selecting dynamic targets, and data-driving your tests.
1. <a href="/features/testing-types/load-testing/running-tests" target="_blank">Run your load test</a>.
1. <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">Analyze your load test results</a>.

<br>
<br>
<br>
<br>

> __Test Studio Training__
><br>
><br>
> Having troubles with your test automation?
> You’ve got the challenges – we have the resources and expertise to help you make testing effective and worthwhile across your organization. Make use of our <a href="https://www.telerik.com/teststudio/training" target="_blank">__free training course or explore the other training options__</a>.

[1]: /img/features/testing-types/load-testing/overview/fig1.png