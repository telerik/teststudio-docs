---
title: Assign Virtual Users
page_title: Assign Virtual Users to the Execution Machine
description: "Manage Virtual Users used in Test Studio load test run. Set virtual users to be used in load test run in Test Studio. Increase/Decrease virtual users amount to be used in Test Studio Load test"
position: 5
---
# Assign Virtual Users for Load Test Execution

Each license of Test Studio includes 100 virtual users to be used by your execution machines (or 20 virtual users in versions prior to 2013.1.nnnn). If you purchase three licenses to Test Studio you can use up to 300 virtual users. To have more than 100 users per license requires you to purchase additional user packs. <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Go to this page</a> to purchase additional virtual user packs. Once purchased and added to your Telerik account, you can assign them to a single execution machine or use these in a setup of multiple execution machines (or load controller).

## Manage the Available Virtual Users

To see and manage the available purchased virtual users, click the **Manage** button in the ribbon bar of an opened load test - the _Manage Virtual Users_ dialog window appears.

![Manage button][1]

### Total Number of Purchased Virtual Users

The total number of virtual users you have purchased along with the number available, or unassigned to any execution machine, will be displayed at the top.

![Purchased and Available users][2]

### Distribution of Virtual Users per Execution Server

The _Distribution of Virtual Users per Execution Server_ section displays all computers added as execution machines and the amount of virtual users assigned to each of these.

> When <a href="/features/testing-types/load-testing/running-load-test/running-tests" target="_blank">running a load test locally</a>, you need to add the local machine and assign virtual users to it. in the case when <a href="/features/testing-types/load-testing/running-load-test/remote-load-test-execution" target="_blank">using multiple machines to run the load scenario</a>, you need to add the machine, which is configured as a Scheduling server and assign sufficient users to that one.

![Purchased and Available users][2a]

## Add New Execution Machine

To add a machine to assign virtual users to, click the __Add local Execution Server__ button and enter the machine name or IP address - do not use localhost or 127.0.0.1 and do not use http or port number. 
 manage another scheduling service or controller, click **Add Scheduling Service** or **Add Controller**, enter the machine name, and click Done.

> As of 2013.1.806, a machine configured as a Scheduling Server and added to assign virtual users to it, is always searched on port 8009. It will not be detected if the Scheduling Service is listening to another port.

![Add Machine][3]

- Once you enter a machine name or IP, hit the _Test Connection_ button. If the IP address or machine name are not correct, or the machine is unreachable in the network, you will not be able to add it as an execution machine.

    ![Add Machine - invalid name or unreachable machine][3a]

- Enter a valid machine name or IP and ensure the computer is reachable in the network. After testing the connection is successful, you can add the machine and assign virtual users to it.

    ![Add Machine - valid machine][3b]

## Assign Virtual Users

- Use the slider bar next to any of the listed machines to add virtual users to it, or to remove virtual users from that controller so they may be used by another scheduling service or controller. Clicking on the left or right of the thumb bar will decrement/increment the number of assigned virtual users.

    ![Slide bar][4]

- To remove a scheduling service or controller from the list, click the **X** on the line for it. Any virtual users that were assigned to it will return to the unassigned pool of virtual users.

    ![X button][5]

- The display of available and assigned users does not dynamically change on its own. Click Refresh to update the display after purchasing additional virtual users or changing the assignment of virtual users on a different computer.

    ![Refresh button][6]

## Buy More Users

If you need to purchase more total users, click **Buy More Users** on the top right corner of the _Manage Virtual Users_ dialog window.

![Buy users][7]

[1]: /img/features/testing-types/load-testing/managing-vu/fig1.png
[2]: /img/features/testing-types/load-testing/managing-vu/fig2.png
[2a]: /img/features/testing-types/load-testing/managing-vu/fig2a.png
[3]: /img/features/testing-types/load-testing/managing-vu/fig3.png
[3a]: /img/features/testing-types/load-testing/managing-vu/fig3a.png
[3b]: /img/features/testing-types/load-testing/managing-vu/fig3b.png
[4]: /img/features/testing-types/load-testing/managing-vu/fig4.png
[5]: /img/features/testing-types/load-testing/managing-vu/fig5.png
[6]: /img/features/testing-types/load-testing/managing-vu/fig6.png
[7]: /img/features/testing-types/load-testing/managing-vu/fig7.png