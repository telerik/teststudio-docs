---
title: Generate Communication Key
page_title: Generate and Update Communication Key
description: Generate Communication Key for the Test Studio Scheduling configuration. Import the new key for all Test Studio components across all involved machines. 
position: 1
---
# Generate New Communication Key 

The **Communication Key** is required by all Test Studio Scheduling components - services and clients, to establish the connection and communicate between each other. You can get the current key or generate a new one in the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling Config wizard</a>. 

<!-- no toc -->
- [Manage the Communication Key](#manage-the-communication-key)
  - [Default Communication Key](#default-communication-key)
  - [Generate New Key](#generate-new-key)
  - [Copy Current Key](#copy-current-key)
- [Generate and Import Key in Single Machine Scheduling Setup](#generate-and-import-key-in-single-machine-scheduling-setup)
- [Generate and Import Key in Multiple Machines Scheduling Setup](#generate-and-import-key-in-multiple-machines-scheduling-setup)

## Manage the Communication Key

Find useful details on the available options to manage the Communication key value.

### Default Communication Key 

The **Communication** tab in the Scheduling Config wizard lets you manage the current key in use or generate and import a new one. 

![Communication key tab](/img/features//scheduling-test-runs/create-scheduling-server/communication-tab.png)

The **Current Key** section indicates which is the key in use. The Scheduling setup is configured to use a default communication key for each Test Studio installation. Thus, after initial install you see the current key is the __Default Key Loaded__. In this configuration you can't copy or see the key. 

![Default Communication key](/img/features//scheduling-test-runs/create-scheduling-server/communication-tab-default-key.png)


### Generate New Key

The **Replace Key** section lets you **Generate** a new key. Once generated, the new value is populated in the text field and is ready to be imported. Hit the **Import** button to replace the current key with the new one. 

![Replace Communication key](/img/features//scheduling-test-runs/create-scheduling-server/communication-tab-replace-key.png)

> **Note**
> <br>
> <br>
> Importing a new key in the Scheduling Config wizard **restarts the Scheduling service on that same machine to apply the new value**. 
> <br>
> <br>
> The Execution Client application is stopped but you need to start it manually. 
> If Test Studio application is also running on the same machine at the time of renewing the communication key, it is not automatically restarted. To apply the recent changes you __need to restart the standalone Test Studio app manually__. 


### Copy Current Key

Once a custom key is generated and imported, the **Current Key** section allows you to copy the value of the key using the __Copy to Clipboard__ button, or see it using the __Show__ button (for the cases when copying is not an option). The key value can be reset to the default value using the __Reset to Default__ button.

> **Important!**
> <br>
> The copied key __must be imported on all machines__ included in the Test Studio Scheduling setup.

![Custom Communication key](/img/features//scheduling-test-runs/create-scheduling-server/communication-tab-custom-key.png)


> **Note**
> <br>
> <br>
> The __communication key is set per machine__. This means that importing a key on one machine lets all other components on the same machine to use it. If you see any troubles with the imported key on a machine, be sure to restart all Test Studio processes. 

## Generate and Import Key in Single Machine Scheduling Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use for the Scheduling service. This triggers restart of the service to take the new key and restart of the Execution client application. 

In the setup where all components of the Scheduling configuration are on the same machine, you only need to restart all Test Studio processes to ensure the new key is imported. Follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Scheduling config wizard</a>. 
1. Switch to the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#communication-tab" target="_blank">Communication tab</a> and generate new communication key. 
2. Hit the **Import** button and wait for a while. 

    ![Generate Key](/img/knowledge-base/scheduling-kb/communication-key/generate-key.png)

3. The Scheduling service is restarted in the background. 
4. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/communication-key/restart-exec-server.png)

5. Restart Test Studio standalone application. 
6. Continue with <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connecting the project to the Scheduler</a> and scheduling test lists. 

## Generate and Import Key in Multiple Machines Scheduling Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use for the Scheduling service. This triggers restart of the service to take the new key and restart of the Execution client application on that same machine. 

In the setup where all components of the Scheduling configuration are on different machines, you need to __import the new key on each machine__. Follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Scheduling config wizard</a> on the machine where the Scheduling service is. 
2. In the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#communication-tab" target="_blank">Communicaion tab</a> generate new communication key. 
3. Hit the **Import** button and wait for a while. 
   
    ![Generate Key](/img/knowledge-base/scheduling-kb/communication-key/generate-key.png)

4. The Scheduling service is restarted in the background. 
5. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> on this machine is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/communication-key/restart-exec-server.png)

6. On this same machine __copy the new key__ value from the __Current Key__ section in the Scheduling config wizard->Communication tab. Be sure to __safely distribute the key as per your local security policies__.

    ![Copy current Key](/img/knowledge-base/scheduling-kb/communication-key/copy-current-key.png)

7. Logon to each of the machine utilized as Execution servers in the Scheduling setup.
8. <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Start the Test Studio Services configuration wizard</a>.
9. Switch to the Communication tab and use the copied key from the Scheduling machine (Step 6. in this list) to import it. Be sure to __safely distribute the key as per your local security policies__.
    
    ![Import new Key](/img/knowledge-base/scheduling-kb/communication-key/replace-key.png)

10. Hit the **Import** button and wait for a while.
11. If running the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/communication-key/restart-exec-server.png)

12. If the machine with the project is a separate machine repeat steps 8. to 10. also for it. If __Test Studio application is running while importing the new key be sure to restart it__. 
13. Continue with <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connecting the project to the Scheduler</a> and scheduling test lists.


