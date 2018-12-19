---
title: Managing Virtual Users
page_title: Managing Virtual Users
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/load-testing/load-managing-users.aspx
position: 21
---
# Managing Virtual Users

Each license of Test Studio includes 100 virtual users to be used by your scheduling server (or 20 virtual users in versions prior to 2013.1.nnnn). If you purchase three licenses to Test Studio you can use up to 300 virtual users. To have more than 100 users per license requires you to purchase additional user packs. <a href="http://www.telerik.com/purchase/teststudio" target="_blank">Go to this page</a> to purchase additional virtual user packs. Once purchased and added to your Telerik.com account, you can assign them to one or more scheduling servers (or load controller) that you have setup.

To manage the virtual users you have purchased, click **Manage** in the **Manage Users** section of the ribbon bar.

![Manage][1]

- The total number of virtual users you have purchased along with the number available to be assigned to scheduling servers or load controllers will be displayed at the top.

![Available users][2]

- The scheduling server or controller you are currently connected to will appear in the list by default. To manage another scheduling service or controller, click **Add Scheduling Service** or **Add Controller**, enter the machine name, and click Done.

> As of 2013.1.806, the Add Scheduling Service dialog always looks for the remote Scheduling Server on port 8009. It will not find a Scheduling Server listening to another port.

![Add scheduling][3]

- Use the slider bar to add virtual users to that scheduling service or controller, or to remove virtual users from that controller so they may be used by another scheduling service or controller. Clicking on the left or right of the thumb bar will decrement/increment the number of assigned virtual users.

![Slidebar][4]

- 
 To remove a scheduling service or controller from the list, click the **X** on the line for it. Any virtual users that were assigned to it will return to the unassigned pool of virtual users.

![X button][5]

- The display of available and assigned users does not dynamically change on its own. Click Refresh to update the display after purchasing additional virtual users or changing the assignment of virtual users on a different computer.

![Balance][6]

If you need to purchase more total users, click **Buy More Users** in the **Manage Users** dialog. 

![Buy users][7]

[1]: /img/features/testing-types/load-testing/managing-vu/fig1.png
[2]: /img/features/testing-types/load-testing/managing-vu/fig2.png
[3]: /img/features/testing-types/load-testing/managing-vu/fig3.png
[4]: /img/features/testing-types/load-testing/managing-vu/fig4.png
[5]: /img/features/testing-types/load-testing/managing-vu/fig5.png
[6]: /img/features/testing-types/load-testing/managing-vu/fig6.png
[7]: /img/features/testing-types/load-testing/managing-vu/fig7.png

