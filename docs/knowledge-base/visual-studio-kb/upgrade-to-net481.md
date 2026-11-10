---
title: Build Errors After Upgrading to Test Studio 2026 Q2 with .NET Framework 4.7.2
page_title: Build Errors After Upgrading to Test Studio 2026 Q2 with .NET Framework 4.7.2
description: "Fix CS0246 build errors for ArtOfTest in Visual Studio after upgrading to Test Studio 2026 Q2. Learn how to upgrade your project's target framework from .NET Framework 4.7.2 to 4.8.1."
position: 2
---
## Build Errors After Upgrading to Test Studio 2026 Q2 with .NET Framework 4.7.2

## Problem

When loading a Test Studio project in Visual Studio that targets **.NET Framework 4.7.2** and building it after upgrading to the **Test Studio 2026 Q2 release**, the build fails with multiple errors.

The **Error List** panel shows errors such as:

> `CS0246` — The type or namespace name 'ArtOfTest' could not be found (are you missing a using directive or an assembly reference?)  
> `CS0246` — The type or namespace name 'Manager' could not be found (are you missing a using directive or an assembly reference?)

![Build errors in Visual Studio Error List](/img/knowledge-base/visual-studio-kb/upgrade-to-net481/fig1.png)

The **Output** window contains a message similar to:

```
The primary reference "ArtOfTest.WebAii" could not be resolved because it was built
against the ".NETFramework,Version=v4.8.1" framework. This is a higher version than
the currently targeted framework ".NETFramework,Version=v4.7.2".
```

## Root Cause

Starting with the Test Studio 2026 Q2 release, the Test Studio assemblies (e.g., `ArtOfTest.WebAii`) are compiled against **.NET Framework 4.8.1**. Projects that still target .NET Framework 4.7.2 cannot resolve these references, resulting in build failures.

## Resolution

To resolve this issue, upgrade your project's target framework to **.NET Framework 4.8.1**.

### Step 1 — Install .NET Framework 4.8.1 (if not already installed)

If .NET Framework 4.8.1 is not yet installed on your machine, you need to add it via **Visual Studio Installer**.

1. Open **Visual Studio Installer**.  
2. Click **Modify** on your Visual Studio installation.

   ![Visual Studio Installer — click Modify](/img/knowledge-base/visual-studio-kb/upgrade-to-net481/fig2.png)

3. Navigate to the **Individual Components** tab.  
4. Search for and select both:
   - **.NET Framework 4.8.1 targeting pack**
   - **.NET Framework 4.8.1 SDK**

   ![Individual Components — select .NET Framework 4.8.1 SDK and targeting pack](/img/knowledge-base/visual-studio-kb/upgrade-to-net481/fig3.png)

5. Click **Modify** to apply the changes and wait for the installation to complete.

> **Note:** If .NET Framework 4.8.1 is already installed, skip Step 1 and proceed directly to Step 2.

### Step 2 — Upgrade the Project Target Framework

1. In **Visual Studio**, right-click your project in the **Solution Explorer** and select **Properties**.  
2. In the **Application** tab, locate the **Target framework** drop-down under the **.NET framework** section.  
3. Select **.NET Framework 4.8.1** from the list.

   ![Project Properties — select .NET Framework 4.8.1](/img/knowledge-base/visual-studio-kb/upgrade-to-net481/fig4.png)

4. A **Target Framework Change** dialog will appear. Click **Yes** to confirm.

   ![Target Framework Change dialog — click Yes](/img/knowledge-base/visual-studio-kb/upgrade-to-net481/fig5.png)

### Step 3 — Rebuild the Project

1. Rebuild the solution (**Build → Rebuild Solution**).  
2. The build should now complete successfully with no framework-related errors.

## Summary

| Step | Action |
|------|--------|
| 1 | (If needed) Install **.NET Framework 4.8.1 SDK** and **targeting pack** via Visual Studio Installer |
| 2 | Change the project **Target Framework** to **.NET Framework 4.8.1** in Project Properties |
| 3 | **Rebuild** the project |
