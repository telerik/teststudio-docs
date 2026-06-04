---
title: Supported Git Commands
page_title: Supported Git Commands
description: "Test Studio Git Integration Supported Built-in Git Commands"
position: 3
---
# Supported Git Commands

## Status Of Project Items

The project view displays the source control status of individual tests.

![Individual Tests](/img/features/source-control/open-tfs-project/fig6.png)

- ![Plus](/img/features/source-control/open-tfs-project/fig7.png) appears next to newly created items (part of a source controlled project) that are not added to the source control yet.
- ![Lock](/img/features/source-control/open-tfs-project/fig8.png)appears next to checked in tests.
- ![Check](/img/features/source-control/open-tfs-project/fig9.png)appears next to checked out tests.

**Note**: The file changes should be always saved in order to get the modified status.

> In general, Test Studio does not check out a project from source control when the project opens. However, if one or more project files are out of date (for example, they were created by an older version of Test Studio), Test Studio will attempt to check them out for an update. This will continue until an up-to-date version of the files are checked into source control.

## Description Of Supported Commands

The Source Control specific commands supported by Test Studio are described below:

- **Commit changes to Git** - commit the changes to your local repository.
- **Push to Git** - push the changes to the remote repository.
- **Pull from Git** - get the latest changes from the remote repository.
- **Discard Local Changes** - undo changes in working folder back to the last commit.
- **Disconnect from Source Control** - disconnects the current project from Source Control.

These could be accessed when right click on any project item and hover **Git Source Control**

![Source Control Context Menu](/img/features/source-control/git/supported-git-commands/fig1.png)

Or alternatively from the Source Control ribbon

![Source Control Ribbon](/img/features/source-control/git/supported-git-commands/fig2.png)


