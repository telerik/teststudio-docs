---
title: Update Test Studio
page_title: Update Test Studio
description: "Test Studio Check for Updates, set automatic check for updates on Test Studio startup"
position: 6
---
# Update Test Studio

Test Studio updates provide new features, improved functionality against evolving controls, interoperability with new software, and bug fixes. The Check for Updates feature allows automatic detection of new versions and provides the option to download and install this new version.

In this article you can find details for the following topics:

- [Instant Check for Updates](#instant-check-for-updates)
- [New Version Available](#new-version-availabele)
- [Enable Check for Updates on Test Studio Startup](#enable-check-for-updates-on-test-studio-startup)

## Instant Check for Updates

#### Test Studio Standalone

In the **Help** drop down in the upper right corner choose the option to **Check for Updates**.

![Help Menu check for updates](/img/general-information/installation/check-for-updates/CheckForUpdatesFull.gif)

Alternatively, you can use the **Check for Updates** button in the **Software Update** section in the <a href="/getting-started/start-a-project/welcome-screen" target="_blank">Welcome Screen</a>.

![Welcome screen check for updates](/img/general-information/installation/check-for-updates/fig2.png)

#### Test Studio Plugin in Visual Studio

If working in Visual Studio with the Test Studio plugin, you can access the update section under the <a href="/features/project-settings/overview" target="_blank">Project Settings</a>.

![Check for Updates in Test Studio Plugin for Visual Studio](/img/general-information/installation/check-for-updates/CheckForUpdatesVisualStudio.gif)

## New Version Available

If Test Studio detects a new release, the new version number appears. To read release notes for this new version, click __What's New?__

![Release notes for detected new version](/img/general-information/installation/check-for-updates/fig3.png)

Use the __Download__ button to get the latest available build.

![Download detected new version](/img/general-information/installation/check-for-updates/fig4.png)

After the download completes, click the __Install__ button to trigger the Installation Wizard.

![Download and install detected new version](/img/general-information/installation/check-for-updates/fig5.png)

The Test Studio Installation Wizard will prepare the installation. The previous version of Test Studio, installed on the machine, is automatically detected and the Wizard prompts with a message to confirm if you wish to upgrade to the newer version. Click __Yes__ to continue with the upgrade.

![Confirm upgrade of the existing installation](/img/general-information/installation/check-for-updates/fig6.png)

> __Note!__ Any running instances of Test Studio, including the Execution Client and Visual Studio loaded with the Test Studio plugin, must be closed during the installation process.

> The upgrade procedure of Test Studio is not affecting the automation projects you work on.

## Enable Check for Updates on Test Studio Startup

Test Studio provides the option to enable automatic check for newer product versions on startup. When ___'Check for Updates on Test Studio Startup'___ option is enabled, a _'Checking for updates...'_ status message will appear at Test Studio startup.

#### Test Studio Standalone

Start Test Studio and choose the __Software Update__ section in the <a href="/getting-started/start-a-project/welcome-screen" target="_blank">Welcome Screen</a>. Enable the checkbox for automatic check for updates and choose whether to be notified for official releases only, or include also internal builds.

![Enable automatic check for updates in Welcome screen](/img/general-information/installation/check-for-updates/fig8.png)

#### Test Studio Plugin in Visual Studio

If working in Visual Studio with the Test Studio plugin, you can access the update section under the <a href="/features/project-settings/overview" target="_blank">Project Settings</a>. The automatic check for updates options are listed in the __Update__ section. Enable the checkbox for automatic check for updates and choose whether to be notified for official releases only, or include also internal builds.

![Enable automatic check for updates in Visual Studio plugin](/img/general-information/installation/check-for-updates/fig7.png)
