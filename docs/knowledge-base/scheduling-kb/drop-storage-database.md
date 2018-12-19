---
title: Drop The Storage Database
page_title: Drop The Storage Database
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Drop The Storage Database

It may happen that the storage database gets corrupted and cannot be updated with the latest changes of your test lists. This can lead in execution of outdated test lists or even inability to execute a test list.

In this situation you should drop the storage database so Test Studio can create a new one. This will ensure fresh storage and in case there are any corrupted entries the tests and test lists will be newly uploaded to the storage.

> Dropping the storage database will lead in loss of the schedule test list results. If the already existing results need to be stored you could drop only the tests and test list collections.

1.&nbsp; Install **Robomongo** which is the official tool for maintaining the MongoDB databases from <a href="https://robomongo.org/" target="_blank">here</a>.

2.&nbsp; Create a connection to the storage database and connect to it.

![Create connection][1]  

3.1.&nbsp; Drop the entire database (if you don't want to lose the already existing results continue to step 3.2). Right click on **TSStorageData** and select drop **Drop Database**

![Drop the entire database][2] 

3.2. If you don't want to loose your schedule results you may drop only **tests** and **testlists** collections.

![Drop the collections][3] 

With the next schedule execution the test lists will be newly uploaded to the storage database.

[1]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig1.png
[2]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig2.png
[3]: /img/knowledge-base/scheduling-kb/drop-storage-database/fig3.png