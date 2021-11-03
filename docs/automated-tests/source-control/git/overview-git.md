---
title: Overview
page_title: Integration with Git Source Control Systems
description: "Test Studio Integration with Git Source Control Systems. Use Git based repository with Test Studio. Use Personal Access token to connect to Git repo accessed with 2FA (two factor authentication). Unable to connect to Git. Error connecting to Git, too many redirects or authentication replays.  "
position: 0
---
# Integration with Git Source Control Systems

Test Studio seamlessly integrates with Git based source control repositories to simplify the collaboration between QAs and developers. The Git integration can also facilitates the work of a QA team on the same test project, allowing them to check-in their work at the same time, but independently.

These are the steps to connect and use a Test Studio project stored in a remote Git repository:

1. Create a dedicated empty repository in the selected Git platform.
<br>
__Note:__ Our recommendation is to use an empty repo to connect the Test Studio project to. This way only Test Studio-related artifacts will be stored within that repo, and the overhead of downloading non-relevant items will be avoided.

1. Choose a Test Studio project, which you want to keep under source control in a Git repository and  <a href="/features/source-control/git/connect-to-git" target="_blank">connect it to Git</a>.

1. Anyone in the team, who need to work on that same project, can use the built-in option to connect to Git and <a href="/features/source-control/git/open-git-project" target="_blank">open the project from the remote repository</a>.
<br>
This action downloads from the remote repo a local copy of the project, which is connected to the remote source controlled project and all changes get tracked.

1. Find other useful topics for Git integration in Test Studio:

- <a href="/features/source-control/git/supported-git-commands" target="_blank">Supported Git commands</a>.
- <a href="/features/source-control/git/branch-management" target="_blank">Branch Management for Git repos</a>.

> **Important**
> <br>
> <br>
> Test Studio provides general support for git repositories -this includes __commit__, __push__, __pull__ and __revert__ commands.
> <br>
> <br>
> Test Studio does not provide any means for creating a repository in a remote provider. Instead, it leaves it up to you to decide in what remote provider you want your projects stored. Having that in mind, you __must first create an empty remote repository__ in a remote provider of choice, and only then <a href="/features/source-control/git/connect-to-git" target="_blank">connect a local project</a> to that repository using Test Studio.
> <br>
> <br>
> If an attempt is made to connect a local project to a remote repository, in which there is an existing project, you need to __manually merge and resolve the conflicting project files__.

## Create Git Remote Repository

The following applies to GitHub.com. Similar workflow is available in other remote repository providers.

![Create an empty repository][1]

## Support for Git Two-Factor Authentication

Nowadays, two-factor authentication is used across different platforms to cover the increasing security policies. Git repositories are often subject of this type of user authentication. The concept of the _Personal Access Token_ is designed to provide an option to connect to the platform programatically and you can use this in Test Studio instead of a password, which requires the second factor authentication.

The following workflow guides you how to __create a personal access token (PAT)__ for a GitHub.com repository, which is accessed using  **two-factor authentication**. Then, that personal access token is used instead of the user password, when connecting to GitHub through Test Studio:

1.&nbsp; Open your GitHub account and navigate to its section __Settings -> Developer settings__.
	
2.&nbsp; Switch to __Personal access tokens__ section and use the __Generate new token__ button to create one.
	
3.&nbsp; Use the generated token to paste it instead a password in the Test Studio _Connect to Git_ dialog.

[1]: /img/features/source-control/git/overview/fig1.png