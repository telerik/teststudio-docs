---
title: Drop The Storage Database
page_title: Drop The Storage Database
description: Drop The Storage Database. The Telerik Storage Database cannot be accessed. Telerik Storage database gets corrupted. This can lead to execution of outdated test lists or even inability to execute a test list. Unable to find test file.  
position: 9
---
# Drop The Storage Database

In certain situations the storage database can get corrupted and cannot be updated with the latest changes of your test lists. This can lead to execution of outdated test lists or even inability to execute a test list due to missing test files. 

In such cases you need to drop the MongoDB database, which will force Test Studio to newly upload the project files to the storage for the next scheduled job.

> Dropping the whole MongoDB database will delete the results of any previous scheduled test list executions. If the already existing results are still necessary, you can drop only single collections.

## Install the MongoDB Compass Tool

Download and install the **MongoDB Compass** tool - the official tool for maintaining the MongoDB databases from <a href="https://www.mongodb.com/try/download/compass" target="_blank">here</a>. Once started, use the default connection string `mongodb://localhost:27017` to connect to the storage database named `TSStorageData` database. 

![Create connection][1]

## Drop the Entire Database

Drop the entire database (this will delete the already existing results from previous scheduled executions). Right click on **TSStorageData** and select drop **Drop Database**

![Drop the entire database][2]

## Drop Single Collections From Database

If you don't want to lose the schedule results you can drop only the following collections: 

- **tests**
- **projects**
- **fs.chunks**
- **fs.files**

![Drop single collections][3]

## Upload Project Files to Storage Database 

Once the database or single collections are dropped, __the upcoming scheduled jobs will not be executed out-of-the-box__ because there is no project in the database to be downloaded on the remote machines. To ensure the upcoming jobs will be executed as expected __you need to upload the project files to the database__ - use the <a href="/automated-tests/scheduling/upload-latest-files" target="_blank">Upload button</a> for this.

[1]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig1.png
[2]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig2.png
[3]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig3.png