---
title: Branch Management For Git
page_title: Branch Management For Git
description: "Test Studio Git integration Branch Management For Git Source Control"
publish: true
position: 4
---
# Branch Management For Git Source Control

Test Studio supports management of Git branches in remote and local repositories.

## Remote Repository

Once a local project is connected to a remote Git repository or a remote project is opened and locally cloned in Test Studio its branches could be managed within Test Studio.

1.&nbsp; Open a source control project enabled for Git.

2.&nbsp; Remote repository supports **Commit**, **Push**, **Pull** and **Discard Local Changes**.

![Remote Available Options][11]

3.&nbsp; The **Manage Branches** dialog could be accessed from the Project Explorer options menu or from the Source Control ribbon.

![Manage Branches Remote Repo][12]

4.&nbsp; The **Manage Branches** dialog contains a list of local and remote branches. The initially created branch is set as default one and is called master.

![Default Remote Branch][13]

5.&nbsp; In the **Manage Branches** dialog a new local branch could be created. Enabling the checkbox "Checkout after creation" will automatically checkout the newly created branch.

![Create Branch Remote Repo][14]

6.&nbsp; The newly created local branch will appear in the respective list and will be marked as current with a red arrow sign in front of its name. Once the dialog is closed the project will be reloaded to display the new branch.

![New Branch Remote Repo][15]

The current branch is also displayed in the **Source Control** ribbon.

![Current Branch][16]

7.&nbsp; The newly created branch will remain local until it is pushed to the remote repository. To do so open the **Manage Branches** window, select the branch to push to remote repository and click the **Push** icon.

![Push New Branch To Remote Repo][17]

8.&nbsp; The refresh button for the list with remote branches will fetch all references from the remote server and clear stale local ones.

![Refresh Remote List][18]

9.&nbsp; If there is a remote branch not present in the local project it could be checked out and a local branch with the same name will be created.

![Checkout Remote Branch][19]

Checkout a remote branch already existing in the local repository will checkout the local branch with the same name.

10.&nbsp; In the case when there are local commits not pushed to the remote branch the local one will be displayed in bold.

![Local Changes Not Pushed][20]

11.&nbsp; In the case when there are remote commits not pulled to the local branch it will be displayed in italic.

![Remote Changes Not Pulled][21]

12.&nbsp; Pull command could be executed against the current checked out branch only. Checkout is grayed out.

![Pull Command][22]

If a branch is not currently checked out the Checkout button is active and Pull is grayed out.

![Checkout][23]

13.&nbsp; Both local and remote branches could be deleted. Since the change is irreversible there is a warning message to confirm your choice.

![Delete][23]

## Local repository

A local project could be also source control enabled using Git and local branches could be maintaned in Test Studio.

1.&nbsp; Open a project in Test Studio, click the **Connect** button in the **Source Control** ribbon. Select **Git**, choose **Local** and fill in the appropriate information click **Connect** and **OK**.

![Connect to Git][1]

2.&nbsp; For local repository only **Commit** is available as an option.

![Available Options][2]

3.&nbsp; The **Manage Branches** dialog could be accessed from the Project Explorer options menu or from the Source Control ribbon.

![Manage Branches][3]

4.&nbsp; The **Manage Branches** dialog contains a list of local branches. The initially created branch is set as default one and is called master.

![Default Branch][4]

5.&nbsp; In the **Manage Branches** dialog a new local branch could be created. Enabling the checkbox "Checkout after creation" will automatically checkout the newly created branch.

![Create Branch][5]

6.&nbsp; The newly created branch will appear in the list and will be marked as checked out with a red arrow sign in front of its name. Once the dialog is closed the project will be reloaded to display the new branch.

![New Branch][6]

7.&nbsp; The current branch name is displayed in the Source control ribbon. It also could be double checked in the **Manage Branches** dialog at any time.

![Current Branch][7]

[11]: /img/features/source-control/git/branch-management/fig2_remote_availableOptions.png
[12]: /img/features/source-control/git/branch-management/fig3_remote_ManageBranches.png
[13]: /img/features/source-control/git/branch-management/fig4_remote_defaultBranch.png
[14]: /img/features/source-control/git/branch-management/fig5_remote_createBranch.png
[15]: /img/features/source-control/git/branch-management/fig6_remote_newBranch.png
[16]: /img/features/source-control/git/branch-management/fig7_currentBranch.png
[17]: /img/features/source-control/git/branch-management/fig6_remote_PushNewBranch.png
[18]: /img/features/source-control/git/branch-management/fig8-refresh.png
[19]: /img/features/source-control/git/branch-management/fig9-checkout-remote-branch.png
[20]: /img/features/source-control/git/branch-management/fig10-commited-locally.png
[21]: /img/features/source-control/git/branch-management/fig11-commited-remotely.png
[22]: /img/features/source-control/git/branch-management/fig12-pull.png
[23]: /img/features/source-control/git/branch-management/fig12-checkout.png
[23]: /img/features/source-control/git/branch-management/fig13-deletel.png

[1]: /img/features/source-control/git/branch-management/fig1_localRepo.png
[2]: /img/features/source-control/git/branch-management/fig2_availableOptions.png
[3]: /img/features/source-control/git/branch-management/fig3_ManageBranches.png
[4]: /img/features/source-control/git/branch-management/fig4_defaultBranch.png
[5]: /img/features/source-control/git/branch-management/fig5_createBranch.png
[6]: /img/features/source-control/git/branch-management/fig6_newBranch.png
[7]: /img/features/source-control/git/branch-management/fig7_currentBranch.png