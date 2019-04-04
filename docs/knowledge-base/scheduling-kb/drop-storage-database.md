---
title: Drop The Storage Database
page_title: Drop The Storage Database
description: Drop The Storage Database. The Telerik Storage Database cannot be accessed. Telerik Storage database gets corrupted. This can lead to execution of outdated test lists or even inability to execute a test list. Unable to find test file.  
position: 1
---
# Drop The Storage Database

In certain situations the storage database can get corrupted and cannot be updated with the latest changes of your test lists. This can lead to execution of outdated test lists or even inability to execute a test list due to missing test files. 

In such cases you should drop the MongoDB database, which will force Test Studio to newly upload the project files to the storage by the next scheduled job.

> Dropping the whole MongoDB database will delete the results of any previous scheduled test list executions. If the already existing results are still necessary, you could drop only the *tests* and *testlists* collections.

## Install the MongoDB Official Maintenance Tool

Download and install the **Robo 3T** - the official tool for maintaining the MongoDB databases from <a href="https://robomongo.org/download" target="_blank">here</a>. Once started, create a connection to the storage database and connect to it - the default values should be sufficient to connect to the TSStorageData databse. 

![Create connection][1]

## Drop the Entire Database

Drop the entire database (this will delete the already existing results from previous scheduled executions). Right click on **TSStorageData** and select drop **Drop Database**

![Drop the entire database][2]

## Drop Single Collections From Database

If you don't want to loose your schedule results you may drop only ***tests*** and ***testlists*** collections.

![Drop the collections][3]

With the next schedule execution the test lists will be newly uploaded to the storage database.

[1]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig1.png
[2]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig2.png
[3]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig3.png