---
title: Executive Dashboard
page_title: Executive Dashboard shows remote test list results
description: "Online results server. Executive Dashboard retulst. View test list results"
position: 7
---
# Executive Dashboard

The **Executive Dashboard** allows you to monitor the results from remotely executed test lists per project. The **Executive Dashboard** gathers the results from the **Storage Server**.

> **Note:** Test lists that are executed locally will not be uploaded to the **Storage Server** automatically. You can publish them to the server, that your project is connected to, from the **Results** tab.

## Installation and Configuration

1. <a href="/general-information/installation/install-procedure" target="_blank">Install the Executive Dashboard components</a> in the **Customize Installation dialog** during Test Studio installation for the machine that will host this service. It is not selected by default in the standalone installation and you can also <a href="/general-information/installation/add-services" target="_blank">add it after that</a>.

    ![Installation Dialog][1]

2. Start Test Studio and click **Configure** in the Scheduling section of the ribbon bar.

    ![Configure][2]

3. Go to the **Executive Dashboard** tab and make configuration changes if necessary. You need to hit the **Apply** button, if you make any changes, and check the details on the bottom of the window. The service will be started automatically. 

    ![Executive Dashboard Configuration][3]

## Executive Dashboard Overview

You can monitor the results from remote test list executions in the brower and on all kinds of devices that can access the Executive Dashboard.

### Project View

In the Project View you see all remotely executed test list results per project. They are sorted first by **Favorites** (the star icon) and then by the **Last Run Start Time** column.
The field selections and favorites are saved locally per browser and per selected project.

![Project View][5]

* **Select project** - Select a Test Studio project from a drop-down list.
* **Refresh interval** - Choose a time interval to refresh the results in the Executive Dashboard.
* **Search field** - Filter test lists by name as you type.
* **Favorites** - Enable/Disable favorites for a test list. Favorite test lists will always appear on top.

Last 10 runs are sorted by time of execution and the latest is on the right side.

### Test Lists View

This view shows you up to 10 remote test list executions at a time and they are sorted by Start Time by default. You can change the sort by clicking the column's header and use multiple rules at the same time.

![Project View][6]

* **Breadcrumb navigation** - Click on the Project name link to navigate back.
* **View Details** - Drill down to the test list details.

### Test List Execution Details

The detailed view of the test list execution shows information about each test. You can sort the results by multiple columns.

![Project View][7]

* **Breadcrumb navigation** - Click on the Project name or the Test List name link to navigate back.
* **Expand Test Details** - Expand the test and view all test steps. If there is a Test as Step, you can expand that further.
* **View Log** - Show the test execution log with option to copy it to clipboard.

![Project View][8]

The version and additional information aboute the Executive Dashboard is available in the **About** button in the header.

![About Page][9]

[1]: /img/general-information/test-results/executive-dashboard/fig1.png
[2]: /img/general-information/test-results/executive-dashboard/fig2.png
[3]: /img/general-information/test-results/executive-dashboard/fig3.png

[5]: /img/general-information/test-results/executive-dashboard/fig5.png
[6]: /img/general-information/test-results/executive-dashboard/fig6.png
[7]: /img/general-information/test-results/executive-dashboard/fig7.png
[8]: /img/general-information/test-results/executive-dashboard/fig8.png
[9]: /img/general-information/test-results/executive-dashboard/fig9.png