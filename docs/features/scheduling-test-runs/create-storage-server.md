---
title: Create a Storage Server
page_title: Create a Storage Server
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/scheduling-test-runs/create-storage-server.aspx, /user-guide/scheduling-test-runs/create-storage-server
position: 4
---
# Create a Storage Server

In a distributed Test Studio installation, the Storage Server is responsible for handling tests and test results for scheduled test runs. It does not need to be on the same machine as any other service or application, although it must be accessible from the <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">Scheduling Server</a>. 

> Storage server uses <a href="https://www.mongodb.com" target="_blank">MongoDb</a> as storage database. MongoDb requires at least 4Gb hard drive space to operate normally.

1.&nbsp;  Install the Storage Service component in the **Customize Installation dialog** during Test Studio Installation for the machine that will host the Storage Service. This component is not selected by default in a Standalone installation.

![Instalation Dialog][1]

2.&nbsp; You must agree the MongoDB license agreement in order to start downloading and install MongoDB.

![License Agreement][8]

3.&nbsp; By default, Test Studio will install and configure automatically MongoDB database on the local machine.

![Install MongoDB][9]


[1]: /img/features/scheduling-test-runs/create-storage-server/fig1.png
[8]: /img/features/scheduling-test-runs/create-storage-server/fig1new.png
[9]: /img/features/scheduling-test-runs/create-storage-server/fig2new.png