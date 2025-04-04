---
title: Open Git Project
page_title: Open Git Project
description: "Open Test Studio Project To Git Source control repository. Use Personal Access token to connect to Git repo accessed with 2FA (two factor authentication). Unable to connect to Git. Error connecting to Git, too many redirects or authentication replays"
publish: true
position: 1
---
# Open Git Project

**Open** Git project in the terms of Test Studio is equal to __cloning an existing repository__. This option creates a local copy of the remote project in the specified folder during establishing connection.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

Follow the steps to open a Test Studio project stored into a remote Git repository.

<br>
<br>

1. Launch any Test Studio project and click the **Open** button in the **Source Control** ribbon.

    ![Connect][1]

    __OR__ 
    <br>
    <br>

    Launch Test Studio and select the option __Open Source Control__ from the <a href="/automated-tests/customize-project/welcome-screen" target="_blank">__Welcome screen__</a>. 

    <br>
    <br>

2. The **Source Control Type** dialog appears. Select **Git**, fill in the authentication details, click **Connect** and **OK**.

    > **Important**
    > <br>
    > <br> We __strongly recommend to <a href="/teststudio/automated-tests/source-control/git/overview-git#using-personal-access-token-for-authentication-in-git-repo" target="_blank">generate a PAT (Personal Access Token)</a> scoped__ for accessing the testing project repository only and use it to connect to the remote repo. 


    ![Connect to TFS][2]

    > **Note**
    > <br>
    > <br>
    > If you are not able to connect to the Git system and get a message _Error connecting to Git, too many redirects or authentication replays_, check if the remote repository requires 2FA to be accessed. Generate a personal access token in your Git account for this repository and use that token instead of the account password.

3. Select a folder where the project will be cloned.

    ![Clone][11]

4. The project and project files are now marked with a ![PLus][4] icon. This indicates it is bound to Source Control.

    ![Connected][3]

5. The <a href="/features/coded-steps/output-panel" target="_blank">**Output panel**</a> includes Source Control tab where you can find additional info for the outcome of commands while using the source control features.

[1]: /img/features/source-control/git/open-git-project/fig1.png
[2]: /img/features/source-control/git/connect-to-git/fig2.png
[3]: /img/features/source-control/git/connect-to-git/fig3.png
[4]: /img/features/source-control/connect-to-tfs/fig4.png
[11]:/img/features/source-control/git/open-git-project/fig6.png
