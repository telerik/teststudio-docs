---
title: Generate Encryption Key
page_title: Generate and Update Encryption Key
description: Generate Encryption Key for Test Studio projects. Import the new key for all Test Studio installations across all involved machines. 
position: 0
---
# Generate New Encryption Key 

The **Encryption Key** is used to secure sensitive data across the Test Studio projects. You can get the current key or generate a new one in the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling Config wizard</a>. 

## Manage the Encryption Key

Find useful details on the available options to manage the Encryption key.

### Default Encryption Key 

The Encryption tab lets you manage the **Encryption Key** which is used to secure sensitive data across the Test Studio projects including: 

- Passwords for connecting to source control repository or bug tracking systems, and database connection strings used in data driven tests;
- Password steps recorded in automated tests when the _'Encrypt'_ step property is enabled. 

![Encryption key tab](/img/features//scheduling-test-runs/create-scheduling-server/encryption-tab.png)

The **Current Key** section indicates which is the key in use. Test Studio installation uses a default encryption key and you see the current key is the __Default Key Loaded__. In this configuration you can't copy or see the key. 

![Default Encryption key](/img/features//scheduling-test-runs/create-scheduling-server/encryption-default-key.png)


### Generate New Key

The **Replace Key** section lets you **Generate** a new key. Once generated, the new value is populated in the text field and is ready to be imported. Hit the **Import** button to replace the current key with the new one. 

![Replace Encryption key](/img/features//scheduling-test-runs/create-scheduling-server/encryption-generate-key.png)

> **Note**
> <br>
> <br>
> When __importing a custom encryption key for the first time__ some of the encrypted data becomes inaccessible. To __continue using your Test Studio projects in such case you must__: 
> * __re-enter all passwords__ for connecting to source control repository or bug tracking systems, and SMTP settings if used in Scheduling configuration;
> * all projects on the machine are __upgraded to use the new key__ for __password steps__ in automated tests when the _'Encrypt'_ step property is enabled and for __database connection strings used in data driven tests__ thus _no further interaction is needed_ for these.

> If you decide to __regenerate the encryption key and import a new one__ all encrypted data becomes inaccessible. To __continue using your Test Studio projects in such case you must__: 
> * __re-enter all passwords__ for connecting to source control repository or bug tracking systems, and database connection strings used in data driven tests, and SMTP settings if used in Scheduling configuration;
> * __re-record all password steps__ in automated tests when the _'Encrypt'_ step property is enabled.


### Copy Current Key

Once a custom key is generated and imported, the **Current Key** section allows you to copy the value of the key using the __Copy to Clipboard__ button, or see it using the __Show__ button (for the cases when copying is not an option).

> **Important!**
> <br>
> The copied key __must be imported on all machines__ where Test Studio is in use.

![Custom Encryption key](/img/features//scheduling-test-runs/create-scheduling-server/encryption-custom-key.png)


> **Note**
> <br>
> <br>
> The __Encryption key is set per machine__. This means that importing a key on one machine lets all projects on the same machine to use it. If you see any troubles with the imported key on a machine, be sure to restart all Test Studio processes. 

## Generate and Import Custom Encryption Key in Single Machine Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use on the current machine. 

In the case when you have only one machine with Test Studio, follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Test Studio Services config wizard</a>. 
2. Switch to the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#encryption-tab" target="_blank">Encryption tab</a> and generate new Encryption key. 
3. Hit the **Import** button and wait for a while. 

    ![Generate encryption Key](/img/knowledge-base/project-configuration-kb/encryption-key/encryption-generate-key.png)

4. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> on this machine is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/Encryption-key/restart-exec-server.png)

5. If running __restart Test Studio standalone application__ and current project in use. When restarted __the project will be upgraded__.
6. If the __project is connected to Git source control__ <a href="/troubleshooting-guide/source-control-problems-tg/fix-git-source-control-lockout-issue-in-test-studio" target="_blank">reset the Git credentials</a>. 
7. If the __project is connected to bug tracking system__ <a href="/features/integration/bug-tracking/configuration" target="_blank">re-enter the credentials in use</a>.
8. If the __current machine is used as Scheduling server__ with <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#automatic-email-notification-for-scheduled-executions" target="_blank">configured SMTP settings, re-enter the credentials in use and apply the change</a>. 
   
    > **Note**
    > <br> 
    > SMTP settings are applied for the machine where the Scheduling service is in use, so you only need to change these once.

9. __Password steps__ in automated tests when the _'Encrypt'_ step property is enabled are upgraded to use the new encryption key. 
10.  __Database connection strings used in data driven tests__ are upgraded to use the new encryption key. 
11. You can continue using the project as before.
 

## Generate and Import Custom Encryption Key in Multiple Machines Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use for current machine.  

In the setup where Test Studio project is used on multiple machines,  you need to __import the new key on each machine__. Follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Test Studio Services config wizard</a> on the machine where the Scheduling service is. 
2. In the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#encryption-tab" target="_blank">Encryption tab</a> generate new Encryption key. 
3. Hit the **Import** button and wait for a while. 
   
    ![Generate encryption Key](/img/knowledge-base/project-configuration-kb/encryption-key/encryption-generate-key.png)

4. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> on this machine is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/Encryption-key/restart-exec-server.png)

5. If running __restart Test Studio standalone application__ and current project in use. When restarted __the project will be upgraded__.
6. If the __project is connected to Git source control__ <a href="/troubleshooting-guide/source-control-problems-tg/fix-git-source-control-lockout-issue-in-test-studio" target="_blank">reset the Git credentials</a>. 
7. If the __project is connected to bug tracking system__ <a href="/features/integration/bug-tracking/configuration" target="_blank">re-enter the credentials in use</a>.
8. If the __current machine is used as Scheduling server__ with <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#automatic-email-notification-for-scheduled-executions" target="_blank">configured SMTP settings, re-enter the credentials in use and apply the change</a>. 
   
    > **Note**
    > <br> 
    > SMTP settings are applied for the machine where the Scheduling service is in use, so you only need to change these once.

9. __Password steps__ in automated tests when the _'Encrypt'_ step property is enabled are upgraded to use the new encryption key. 
10. __Database connection strings used in data driven tests__ are upgraded to use the new encryption key. 
11. If the current project is under source control __push the latest changes to the remote repository__. 
12. On this same machine __copy the new key__ value from the __Current Key__ section in the Test Studio Services config wizard->Encryption tab. Be sure to __safely distribute the key as per your local security policies__.

    ![Copy current Key](/img/knowledge-base/project-configuration-kb/encryption-key/copy-encryption-key.png)

13. __Logon to each of the machines__ where Test Studio is in use.
14. <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Start the Test Studio Services configuration wizard</a>.
15. Switch to the Encryption tab and use the copied key from your local machine (Step 10. in this list) to import it. Be sure to __safely distribute the key as per your local security policies__.
    
    ![Import new Key](/img/knowledge-base/project-configuration-kb/encryption-key/encryption-import-key.png)

16. Hit the **Import** button and wait for a while.
17. If running the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> is restarted. 
   
    __Note!__ You may see a message that the Execution server app is closed and you need to start it manually. 

    ![Restart Execution server](/img/knowledge-base/scheduling-kb/Encryption-key/restart-exec-server.png)

18. Repeat steps 13. to 17. for all machines where Test Studio is in use. If __Test Studio application is running while importing the new key be sure to restart it__. 
19. Continue with __getting the latest version of the project__ from the source control in use and recording/running tests. If the machine is used for test execution as part of the Test Studio Scheduling setup, you need to <a href="/automated-tests/scheduling/upload-latest-files" target="_blank">upload the latest state of project in the Storage database</a>. 

## Re-Generate the Custom Key 

If you decide to __re-generate the custom encryption key__ and replace it with a new one, be informed that __all encrypted data becomes inaccessible__. This means you need to also re-record all password steps across the automated tests and re-enter database connection strings used in data driven testing along with re-entering Git, bug tracking system and SMTP credentials. 

You can follow the steps described for single machine setup or multiple machines configuration listed above with the only change in steps 9. and 10. as follows: 

* __Password steps must be re-recorded__ in automated tests when the _'Encrypt'_ step property is used. 
    
    > __Tip!__ 
    > <br>
    > You can use the option to <a href="/features/custom-steps/overview#add-step-for-a-recorded-element" target="_blank">add steps for an existing element</a> in the elements repository to re-create the step. Another possible approach is to use <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">the partial test run options</a>. 

* __Database connection strings used in data driven tests__ must be <a href="/features/data-driven-testing/add-data-source#add-a-database-source" target="_blank">re-entered</a>.
