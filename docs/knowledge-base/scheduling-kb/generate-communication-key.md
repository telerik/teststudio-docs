---
title: Generate Communication Key
page_title: Generate an Update Communication Key
description: Generate Communication Key for the Test Studio Scheduling configuration. Import the new key for all Test Studio components across all involved machines. 
position: 1
---
# Generate New Communication Key 

The **Communication Key** is required by all Test Studio Scheduling components - services and clients, to establish the connection and communicate between each other. You can get the current key or generate a new one in the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server" target="_blank">Scheduling Config wizard</a>. 

## Copy Current Key 

The **Communication** tab in the Scheduling Config wizard lets you manage the current key in use or generate and import a new one. 

![Current Key](/img/knowledge-base/scheduling-kb/communication-key/copy-current-key.png)

The **Current Key** section allows you to **Copy to Clipboard** the current key in use or **Show** its value (for the cases when copying is not an option). The copied key can be imported for the other components of the setup - the **Test Studio Test Runner** application on the Execution machines, and the project connect wizard.

> **Note**
> <br>
> <br>
> The communication key is set per machine. That means when you add the key for one component, it gets used for all other components on the same machine after resatrting the process.

## Generate New Key

The **Replace Key** section lets you **Generate** a new key. Once generated, the new value is populated in the text field and is ready to be imported. 

![Generate Key](/img/knowledge-base/scheduling-kb/communication-key/replace-key.png)

### Importing New Key in Single Machine Scheduling Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use for the Scheduling service. This triggers restart of the service to take the new key and restart of the Execution client application. 

In the setup where all components of the Scheduling configuration are on the same machine, you only need to restart all Test Studio processes to ensure the new key is imported. Follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Scheduling config wizard</a>. 
1. In the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#communication-tab" target="_blank">Communicaion tab</a> generate new communication key. 
1. Hit the **Import** button and wait for a while. 
1. The Scheduling service is restarted in the background. 
1. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> is restarted. 
1. Restart Test Studio standalone application. 
1. Continue with <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">connecting the project to the Scheduler</a> and scheduling test lists. 

### Importing New Key in Multiple Machines Scheduling Setup 

Once you generate a new key, hit the **Import** button to replace the current key in use for the Scheduling service. This triggers restart of the service to take the new key and restart of the Execution client application on that same machine. 

In the setup where all components of the Scheduling configuration are on different machines, you need to __import the new key on each machine__. Follow the below steps: 

1. Open the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#start-the-test-studio-scheduling-config-wizard" target="_blank">Scheduling config wizard</a> on the machine where the Scheduling service is. 
1. In the <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-scheduling-server#communication-tab" target="_blank">Communicaion tab</a> generate new communication key. 
1. Hit the **Import** button and wait for a while. 
1. The Scheduling service is restarted in the background. 
1. The <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Execution client application from the system tray</a> on this machine is restarted. 
1. Copy the new key value. 
1. Logon to each Execution machine and <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#execution-server-configuration" target="_blank">import the new key</a> value in the Execution client application from the system tray. 
1. On the machine with the project <a href="/automated-tests/scheduling/connect-to-scheduling-server" target="_blank">open the **Scheduling Server Settings** window by clicking the **Connect** button</a>. 
1. Import the new communication key and connect to the Scheduling server. 
1. Once the connection is successful you can confirm the setup and continue with scheduling test lists. 

