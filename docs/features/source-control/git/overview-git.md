---
title: Overview
page_title: Integration with Git Source Control Systems
description: "Test Studio Integration with Git Source Control Systems"
position: 0
---
# Integration with Git Source Control Systems

Test Studio seamlessly integrates with Git Source Control to simplify the collaboration between QAs and Developers. The Git integration also facilitates the work of a QA team on the same test project, allowing them to check-in their results at the same time and independently. In addition to Git support, Test Studio can also interact with any other file-based source control system.

> Test Studio provides general support for git repositories. It supports commit, push, pull and revert commands. However, it does not provide means for creating a repository in any remote provider. Instead, it leaves it up to you to decide in what remote provider you want your projects stored. Having that in mind, you must first create an empty remote repository in a remote provider of choice, and only then connect a local project to that repository using Test Studio. If an attempt is made to connect a local project to a different existing remote one, you might have to manually merge the conflicting project files.

- <a href="/features/source-control/git/connect-to-git" target="_blank">Connect a local project to Git</a>
- <a href="/features/source-control/git/open-git-project" target="_blank">Open a Git-controlled project</a>
- <a href="/features/source-control/git/supported-git-commands" target="_blank">Supported Git commands</a>
- <a href="/features/source-control/git/branch-management" target="_blank">Branch Management for Git repos</a>

## Configure Git Remote Repository

The following applies to GitHub.com. Similar workflow is available in other remote repository providers. 

![Create an empty repository][1]

## Personal Access Token

The following is applicable if the GitHub.com repository is accessed with **two-factor authentication**.

A personal access token should be created and used instead of password when connecting to GitHub through Test Studio:

1.&nbsp; Open your GitHub account Settings -> Developer settings
	
2.&nbsp; Choose Personal access tokens -> Generate new token
	
3.&nbsp; Once the token is generated and copied to clipboard paste it to the password field in Test Studio connect to Git dialog.

[1]: /img/features/source-control/git/overview/fig1.png