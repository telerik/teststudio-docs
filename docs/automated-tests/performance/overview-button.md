---
title: Overview View
page_title: Performance Testing Overview View
description: "Overview View of performance test results in Test Studio."
position: 3
---
# Overview Button

Click the **Overview** button in the **Views** ribbon. Each step of the Performance Run is listed as a row in the grid.

![Overview][1]

- Click a column header representing characters or digits to sort by that column.
- Use the trophy icon to assign or unassign this Run as the Benchmark. 
- Click the **Description** field for a step to see its Details. 

---

- **Total Step Time** = (Time that the Step Ended Execution + Time for the Next Step's Element to be Located) − Time that the Step Started Execution.
- **Server Time** = the time during step execution than an HTTP Request or Response was actively being processed by the Test Studio Proxy. 
  - Overlapping requests are not counted twice.
- **Client Time** = Total Step Time − Server Time. (Test Studio only records Total Step Time and Server Time.)
- **Size** = the amount of data processed for Server Time.


[1]: /img/features/testing-types/performance-testing/overview-button/fig1.png