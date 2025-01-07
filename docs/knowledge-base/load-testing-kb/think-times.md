---
title: Think Times
page_title: Think Times
description: Think times in Test Studioo Load test represents the time it takes a user to process the information received from the application and decide what to do next. It also represents other delays, like the amount of time spent filling in a form before submitting the content. Advantages if choosing the right Think Times in Test Studio load test. 
position: 1
---
#Think Times

In Test Studio Load Tests, <a href="/features/testing-types/load-testing/think-times" target="_blank">Think Time</a> represents the time it takes a user to process the information received from the application and decide what to do next. It also represents other delays, like the amount of time spent filling in a form before submitting the content.

## Advantages 

There are several advantages to choosing the right Think Times.

**Think Times Improve Accuracy**. Because real users do not submit their requests at high speed, Think Times improve the accuracy of your Load Test user profile. This contributes to the overall accuracy of your Load Test results.
 
**Think Times Improve Performance**. Think Time frees up Execution Server machine resources between requests. This allows other VUs on the Execution Server to transmit their requests, and prevents the Execution Server machine from becoming <a href="https://www.gartner.com/it-glossary/io-bound" target="_blank">I/O bound</a>.

**Think Times Enable the Use of Dynamic Targets**. Some Load Tests need <a href="/features/testing-types/load-testing/dynamic-targets" target="_blank">Dynamic Targets</a> to properly simulate user scenarios. Because Dynamic Targets are contained in the responses from the server, Test Studio needs to wait for the server to respond before it can extract the Dynamic Target values. Including Think Times in your Load Test helps ensure there is sufficient time after responses for Dynamic Targets to function properly.

## Using Think Times 

Think Times are flexible, so consider how best to use them.

### Vary Think Times 

Because every user is different, accurate load tests need a range of Think Time values. For example, some users take longer to read or enter data into a form than others. Test Studio can automatically vary the Think Time based on a deviation time specified with the Think Time. This will more accurately replicate the length of time from when a person receives a response from your server to the time that person requests a new page.

### Choose a Realistic Think Time Range 

A usual deviation will be anywhere from 10 to 120 seconds, depending on the specific user scenario. A good approach to determine what this range should be for any specific webpage is to study the logs of your website and determine what is the median amount of time users spend on the page and the ranges of variations from this median.


##See Also

* <a href="/features/testing-types/load-testing/think-times" target="_blank">Think Times How-To article</a>

* <a href="/features/testing-types/load-testing/dynamic-targets" target="_blank">Dynamic Targets</a>


