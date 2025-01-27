---
title: Pages Not Defined
page_title: Pages Not Defined
description: "Executing a Test Studio coded test is not possible due to errors 'Type Pages is not defined' or 'The type or namespace name Pages could not be found'. How to resolve this type of errors"
position: 1
---
# Pages Not Defined

## Problem

When I execute my test in the Standalone version, or build my test project in the VS plugin, I receive one of the following errors:

- Type 'Pages' is not defined
- The type or namespace name 'Pages' could not be found

## Cause

The coded files need to use the namespace as the one set on project level in the <a href="/features/project-settings/overview)" target="_blank">Project settings</a> under the Script tab. The issue usually appears if the coded files are copied within a new project and not inserted through the <a href="/features/project-explorer/overview#project-context-menu-options" target="_blank">Project Explorer options to add existing test, or coded file</a>. 

The code-behind file for a test in project with name TestProj2 looks like this: 

```C#

// Starting with a list of using statements which may vary 
// and therefore are not listed here

namespace TestProj2 // This is the namespace set in the project settings
{

	// This is the class name which matches the test name in which the coded step was created
    public class KendoReactCombobox : BaseWebAiiTest 
    {
        #region [ Dynamic Pages Reference ]

        private Pages _pages;

        /// <summary>
        /// Gets the Pages object that has references
        /// to all the elements, frames or regions
        /// in this project.
        /// </summary>
        public Pages Pages
        {
            get
            {
                if (_pages == null)
                {
                    _pages = new Pages(Manager.Current);
                }
                return _pages;
            }
        }

        #endregion
        
        // Add your test methods here...


	}

}
```

## Solution

* One option is to fix the errors __set the namespace in the code-behind file to match the one in the Project settings__. 

* The other option is to remove the test from the project and add it again using the option to add existing test. Follow the step below: 
  1. Delete the test from project through the <a href="/features/project-explorer/overview#project-context-menu-options" target="_blank">Project Explorer context menu options</a> -> *Delete*.
  2. Now use the <a href="/knowledge-base/best-practices-kb/add-existing-test" target="_blank">Project Explorer option to add an existing test file into the project</a> and choose the original test file you need to add.



