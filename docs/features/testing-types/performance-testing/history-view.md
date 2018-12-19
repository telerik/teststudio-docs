---
title: History View
page_title: History View
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/performance/history-view.aspx, /user-guide/performance/history-view
position: 2
---
# History View

Click the **History** button in the **Views** ribbon. Each Performance Run is listed as a row in the grid. Click a column header to sort by that column. Each Run is also represented on the line graph below the grid.

![History View][1]

The first column of the grid shows a chart icon. Click that icon for the Run you wish to establish as your performance baseline. Only one run can be designated as the Benchmark.

![Benchmark][2]

Click the **Date** field for a Run to see its Overview.

![Date][3]

The last column of the grid shows a delete icon. Click that icon to send that Performance Run to the Recycle Bin. Once in the Recycle Bin, Runs can be restored or permanently deleted.

![Delete][4]

- Performance Run files have a .tsperf file extension.
- The file name consists of a string of digits and the machine name, for example:
  - 129591225988564221 MACHINE1.tsperf
- The original location is the file path set in <a href="/features/testing-types/performance-testing/gather-perfomance-data" target="_blank">Set Up > Configure</a> under section 1: Basics. 
- .tsperf files cannot be opened on their own. They simply hold the data seen in the different Performance views.



[1]: /img/features/testing-types/performance-testing/history-view/fig1.png
[2]: /img/features/testing-types/performance-testing/history-view/fig2.png
[3]: /img/features/testing-types/performance-testing/history-view/fig3.png
[4]: /img/features/testing-types/performance-testing/history-view/fig4.png

