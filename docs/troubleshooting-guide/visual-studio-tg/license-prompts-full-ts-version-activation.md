---
title: Wrong License Activation Prompt in Test Studio Dev Edition
page_title: Test Studio Dev Edition Wrongly Prompts Activating Trial License
description: "Learn how to resolve the wrong license activation prompt in Test Studio Dev Edition after upgrading the Visual Studio plugin. This guide provides a solution to address issues with unexpected trial license activation prompts."
position: 1
---
# Wrong License Activation Prompt in Test Studio Dev Edition

## PROBLEM

After upgrading __Test Studio Dev Edition plugin in Visual Studio from release Q1 2025 (v. 2025.1.226)__ it prompts for license activation but the wizard suggests activating Test Studio Ultimate trial version only. 

## SOLUTION


To resolve the wrong license activation prompt in Test Studio Dev Edition, you can try one of the following options:

### Option 1: Repair the Test Studio Dev Edition Installation

1. Exit **Visual Studio** to ensure no conflicts during the repair process.
1. Open the **Windows Control Panel**.
2. Navigate to **Programs and Features**.
3. Locate the **Test Studio Dev Edition** in the list of installed applications.
4. Select the application and click **Repair**.
5. Follow the on-screen instructions to complete the repair process.

### Option 2: Perform a Fresh Install of Test Studio Dev Edition

1. Exit **Visual Studio** to ensure no conflicts during the installation process.
2. Open the **Windows Control Panel** and navigate to **Programs and Features**.
3. Locate and uninstall the **Test Studio Dev Edition** application.
4. Download the latest available version of **Test Studio Dev Edition** from the official website.
5. Run the installation file and follow the on-screen instructions to complete the setup.

After completing either of these steps, restart Visual Studio and verify that the license activation prompt now lets you choose your available Test Studio Dev Edition license.