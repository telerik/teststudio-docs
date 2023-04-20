---
title: Missing Page Elements
page_title: Resolve a Missing Page Elements Error
description: "Resolve a Missing Page Elements Error when trying to run Test Studio test"

position: 1
---
# Resolve a Missing Page Elements Error

## PROBLEM

I am unable to build a Test Project (executing a test in the Standalone version also builds the entire project) that contains coded steps because of a compilation error related to missing elements:

![Error][1]

This error can be encountered in either the Standalone version or the VS plugin.

## SOLUTION

Most recorded actions are associated with an element from the application being tested. Test Studio needs to locate each element before a test step against it can be executed. To that end, all elements are stored in the <a href="/knowledge-base/project-configuration-kb/element-repository" target="_blank">Elements Repository</a>.

If you click on a particular step within your test, a yellow arrow will point out which element in the Repository is associated with this step (unless it's not associated with an element):

![Element][2]

It's also possible to access the elements in the Repository from a coded step. This saves you the effort of writing Find Logic from scratch. Instead, you're reusing logic Test Studio initially generated. Similarly, if you convert a regular step to code, the generated coded step will access the associated element from the Repository (e.g. *Pages.Bing.BingDiv*). 

Compilation errors will occur if the code is trying to access an element that doesn't exist in the Repository. There are a few situations where this can occur:

-  **You deleted the element.**

Test Studio will not let you delete an element as long as a regular step is associated with it. However, Test Studio cannot detect whether you're referencing the element in code and will let you delete it if only a coded step is referencing the element. This will lead to a compilation error. This problem might arise if you convert a specific step to code. This will erase the connection to the element. The element will not be removed from the repository, but Test Studio will let you manually delete it. Also, elements added through the <a href="/features/elements-menu/overview" target="_blank">Add to Project Elements</a> feature can be removed because they're not associated with elements to begin with.
 

To resolve this, either add the required element in the Repository or rewrite the code to include Find Logic. For instance, let's say the following code (inteded to run against Google's main page) does not compile:

	Pages.Bing.BingDiv.Click(false)

You can rewrite it like this:


	Find.ById<HtmlDiv>("binglogo").Click(false)

- **You pasted code between coded steps belonging to different Test Projects.**

Each Test Studio test contains a resource file which hold the Elements Repository for that test. You should import only entire tests by using Import/Export from the GUI when working with more than one test. Again, you can resolve this by adding the necessary element or rewriting the code as seen above.


[1]: /img/troubleshooting-guide/test-execution-problems-tg/missing-page-elements/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/missing-page-elements/fig2.png
