---
title: Missing Execution Server
page_title: Missing Execution Machine
description: "Missing Execution Machine in Test Studio Scheduling setup. A machine configured as Execution server is not listed in the Execution status view "
position: 1
---
# Missing Execution Machine

## PROBLEM

I open the Machine status view to see the Execution server machines and one of the Execution Machine is missing from the list.

## SOLUTION

1. __The Execution Server may not be running.__ 
   - <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#start-the-execution-client" target="_blank">Start the Test Studio Execution client application</a> on the remote execution machine.
2. __The Execution Client app may not be registered to the Scheduling Server.__
  - <a href="/automated-tests/scheduling/multiple-machines-scheduling-setup/create-execution-server#configure-test-studio-execution-client" target="_blank">Configure the Test Studio Execution client application</a> on the remote execution machine to connect to the Scheduling service in use. 

