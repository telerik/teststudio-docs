---
title: Connect Project To Git
page_title: Connect Project To Git
description: "Connect Test Studio Project To Git Source control repository"
publish: true
position: 2
---
# Connect Project To Git

**Connect** Git project in the terms of Test Studio is to be applied when you should share an existing local project for first time to an empty remote repository. This option will sync the tracking of master branch and will push all changes to the remote repo. **Connect** could be also used if a project's source control binding was removed to connect it to its corresponding remote repository. However if there are changes made in between and some files are conflicting you might need to manually merge the conflicting project files.

## Connect To Remote Repository

1.&nbsp; Open a project in Test Studio Standalone version.

2.&nbsp; On the **Project** tab, click the **Connect** button in the **Source Control** ribbon.

![Connect][1]

3.&nbsp; The **Connect to Source Control** dialog appears. Select **Git**, fill in the appropriate information click **Connect** and **OK**.

**Two-step authentication** flow for GitHub is supported using <a href="/features/source-control/git/overview-git#Personal-Access-Token" target="_blank">a personal token</a> instead of the account password.

You can choose between local and remote repository. For the local repository the local project path is set by default.

> An empty remote repository should have already been created as described in the <a href="/features/source-control/git/overview-git" target="_blank">Overview</a> page. A Test Studio project is mapped to a single remote repository.

![Connect to Git][2]

4.&nbsp; The project and project files are now marked with a ![PLus][4] icon. This indicates it is bound to Source Control.

![Connected][3]

5.&nbsp; The <a href="/features/coded-steps/output-panel" target="_blank">**Output panel**</a> includes Source Control tab where furhter useful info could be found while using the source control features.

## Connect To Local Repository

1.&nbsp; Open a project in Test Studio, click the **Connect** button in the **Source Control** ribbon. Select **Git**, choose **Local** and fill in the appropriate information click **Connect** and **OK**. Working directory will be set automatically to the local project path.

![Connect to Git Local Project][5]

## Connect Local Git Enabled Project To An Empty Remote Repository

A local Git project could be also connected to a remote repository at any time. It is recommended to use an empty repository to avoid conflicts. If you decide otherwise all possible conflicts should be resolved manually.

1.&nbsp; Open the local Git project and remove the Source Control Binding.

![Connect to Git Local Project][6]

2.&nbsp; Once the bidning is removed follow the above described steps to <a href="/features/source-control/git/connect-to-git#Connect To Remote Repository" target="_blank">connect a project to a remote repository</a>.

[1]: /img/features/source-control/git/connect-to-git/fig1.png
[2]: /img/features/source-control/git/connect-to-git/fig2.png
[3]: /img/features/source-control/git/connect-to-git/fig3.png
[4]: /img/features/source-control/connect-to-tfs/fig4.png
[5]: /img/features/source-control/git/branch-management/fig1_localRepo.png
[6]: /img/features/source-control/git/connect-to-git/fig4_removeSC.png