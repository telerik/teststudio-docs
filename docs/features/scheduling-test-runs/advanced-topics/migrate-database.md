---
title: Migrate from SQL to MongoDB
page_title: Migrate from SQL to MongoDB
description: "Test Studio MongoDB storage service. Transfer old SQL results (prior 15th of October 2015) to the new Mongo database"
position: 4
---
# Migrate from SQL to MongoDB

Since Test Studio R3 release in October 2015 (v.2015.3.1015) we have introduced a new improved storage server using MongoDB database instead of SQL database. You will be able to transfer your old results (prior 15th of October 2015) to the new Mongo database using <a href="http://docs.telerik.com/teststudio/downloads/DbMigratorExe.zip">this tool</a>. 

> Note that you must have the <a href="http://docs.telerik.com/teststudio/features/scheduling-test-runs/create-storage-server" target="_blank">Storage Server</a> already configured.

Once you download the tool, extract the content on your hard drive and run the DBMigrator.exe

![DBMigrator.exe][1]

The tool will open and you will have to fill the following fields:

![Mogration tool][2]

- Source - this should be the SQL connection string you were using to connect to your SQL database
- Destination - this is the new MongoDB connection string

> You can get both connection strings from the following file: **CloudStorageSelfHost.exe.config** located in:
> *C:\Program Files (x86)\Telerik\Test Studio\StorageService*

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

Once you fill the fields as demonstrated above click the **Migrate** button. You will have to allow certain time (depends on how large is your database) in order to migrate the results to the MongoDB database.

![wait][3]

Once done you should be able to view your scheduling results in the <a href="http://docs.telerik.com/teststudio/getting-started/test-results/calendar" target="_blank">Calendar</a> after clicking the Reload button.

[1]: /img/features/scheduling-test-runs/migrate-database/fig1.png
[2]: /img/features/scheduling-test-runs/migrate-database/fig2.png
[3]: /img/features/scheduling-test-runs/migrate-database/fig3.png