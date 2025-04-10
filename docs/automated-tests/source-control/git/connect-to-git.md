---
title: Connect Project To Git
page_title: Connect Project To Git
description: "Connect Test Studio Project To Git Source control repository. Use Personal Access token to connect to Git repo accessed with 2FA (two factor authentication). Unable to connect to Git. Error connecting to Git, too many redirects or authentication replays"
published: true
position: 2
---
# Connect Project To Git

**Connect project to Git** in the terms of Test Studio is used when you need to push an existing local project for first time to an empty remote repository. This option syncs the tracking of the main branch and lets you push all changes to the remote repo. 

The **Connect to Git** option can be used also to reconnect a project to its corresponding remote repository when the project's source control binding was removed. However if any changes made while the project was disconnected are conflicting with the repo, you need to manually resolve these conflicting project files.

## Connect To Remote Repository

1. Open a project in Test Studio Standalone version.

2. On the **Project** tab, click the **Connect** button in the **Source Control** ribbon.

    ![Connect][1]

3. The **Connect to Source Control** dialog appears. Select **Git**, fill in the authentication details, click **Connect** and **OK**.

    > **Important**
    > <br>
    > <br> We __strongly recommend to <a href="/teststudio/automated-tests/source-control/git/overview-git#using-personal-access-token-for-authentication-in-git-repo" target="_blank">generate a PAT (Personal Access Token)</a> scoped__ for accessing the testing project repository only and use it to connect to the remote repo.

4. You can choose between local and remote repository. For the local repository the local project path is set by default.

    > An empty remote repository should have already been created as described in the <a href="/features/source-control/git/overview-git" target="_blank">Overview</a> page. A Test Studio project is mapped to a single remote repository.

    ![Connect to Git][2]

    > **Note**
    > <br>
    > <br>
    > If you are not able to connect to the Git system and get a message _Error connecting to Git, too many redirects or authentication replays_, check if the remote repository requires 2FA to be accessed. Generate a personal access token in your Git account for this repository and use that token instead of the account password.

5. The project and project files are now marked with a ![PLus][4] icon. This indicates it is bound to Source Control.

    ![Connected][3]

6. The <a href="/features/coded-steps/output-panel" target="_blank">**Output panel**</a> includes Source Control tab where you can find additional info for the outcome of commands while using the source control features.

## Connect To Local Repository

1. Open a project in Test Studio, click the **Connect** button in the **Source Control** ribbon. Select **Git**, choose **Local** and fill in the appropriate information click **Connect** and **OK**. Working directory will be set automatically to the local project path.

    ![Connect to Git Local Project][5]

## Connect Local Git Enabled Project To An Empty Remote Repository

You can connect a local Git project to a remote repository at any time. Our recommendation is to use an empty repository to avoid conflicts. If you decide otherwise you need to resolve all possible conflicts manually.

1. Open the local Git project and remove the Source Control Binding.

    ![Connect to Git Local Project][6]

2. Once the local binding is removed follow the above described steps to <a href="/features/source-control/git/connect-to-git#Connect To Remote Repository" target="_blank">connect a project to a remote repository</a>.

[1]: /img/features/source-control/git/connect-to-git/fig1.png
[2]: /img/features/source-control/git/connect-to-git/fig2.png
[3]: /img/features/source-control/git/connect-to-git/fig3.png
[4]: /img/features/source-control/connect-to-tfs/fig4.png
[5]: /img/features/source-control/git/branch-management/fig1_localRepo.png
[6]: /img/features/source-control/git/connect-to-git/fig4_removeSC.png