---
title: Upgrade Existing MongoDB to Version 4.0
page_title: Upgrade Existing MongoDB to Version 4.0
description: Upgrade an existing MongoDB version lower than 3.6 to MongoDB version 4.0 or higher. Problems with starting MongoDB service. Not able to use Test Studio Scheduling feature. MongoDB service unable to start. 
position: 0 
---
# Upgrade Existing MongoDB to Version 4.0

MongoDB is a third party tool used by Test Studio to store the project files required for scheduling tests on remote machines. We strive to keep this working out of the box, though there are upgrades of the Mongo, which affect the database used by Test Studio.

If you upgrade an existing MongoDB installation with version lower than 3.6 to MongoDB with version 4.0 or higher you may experience problems with starting MongoDB service and this not being able to use Test Studio Scheduling feature. The behavior is expected and is not Test Studio related. The official Mongo upgrade procedure can be found <a href="https://docs.mongodb.com/manual/release-notes/4.0-upgrade-standalone/" target="_blank">here</a>.

## MongoDB Backup-Restore from 3.x to 4.x

What we found working quite well for us is to backup your existing database and then restore it.

#### 1. Stop the MongoDB Service

Open the Windows services and manually stop the MongoDB service.

![Stop Service][1]

#### 2. Delete the MongoDB Windows Service

Start a Command Prompt as Administrator and type the following command:
 
```
sc delete MongoDB
```

![Delete Service][2]

#### 3. Backup the Database

Start a Command Prompt as Administrator and change the directory to the bin/ folder in the 3.x  MongoDB installation directory. Run the following command:

```
mongodump --db TSStorageData
```

The result is a dump/ folder where the command is run, which contains the dump of the TSStorageData database.

#### 4. Restore the Database

Once the backup is ready, start with install of 4.x MongoDB server. Then copy dump/ folder to the bin/ in installation folder of the 4.x MongoDB server. Start a Command Prompt as Administrator and change the directory to the bin/ folder of the 4.x MongoDB installation, run the following command:

```
Mongorestore dump/
```

Run <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">Configure Scheduling Server wizard</a> and change the *mongod.exe* path to the newly installed 4.x MongoDB, then click on *Apply*. Start MongoDB service, if stopped.

[1]: /img/knowledge-base/scheduling-kb/upgrade-to-mongo-4-0/fig1.png
[2]: /img/knowledge-base/scheduling-kb/upgrade-to-mongo-4-0/fig2.png
