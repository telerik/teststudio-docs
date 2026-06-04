---
title: Exported Results
page_title: Exported Results
description: What exported Load results show. Overall Test Statistics. HTTP Statistics by URI. Status Codes by URI.
position: 1
---
## Understand Exported Load Results

The Test Studio Load Test <a href="/features/testing-types/load-testing/analyzing-results" target="_blank">Analysis Screen</a> displays graphical results. If you export your load test results in HTML or .XLSX format, the results appear as a table. This document contains tips on interpreting this data.

## Sections of the Exported Results

The tabular format of Test Studio Load Test includes three different formats of data. In .XLSX format, these appear as different tables; in HTML, they appear in the same page.

### Overall Test Statistics

This table provides data for all the sequential polling points for the load test. The Timestamp column displays the time when the data occurred.

### HTTP Statistics by URI

This table provides timing, data and HTTP error count statistics for each URI over time.

* **Average Response Time (ms)** - this column displays the average response time in milliseconds for requests to the URI.

### Status Codes by URI 

This table provides counts for each different HTTP status codes by sequence and URI. 

* **Count** - this shows the cumulative number of times an error code has been received for a particular URI.