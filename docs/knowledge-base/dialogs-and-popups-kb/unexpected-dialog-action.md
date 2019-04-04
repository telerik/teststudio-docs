---
title: UnexpectedDialogAction
page_title: UnexpectedDialogAction
description: Handle any unexpected dialogs if such appear during test list execution. 
position: 1
---
#Avoiding Dialog Handling Problems with the UnexpectedDialogAction Feature#

I am running tests as part of a test list. I am having trouble with dialog handler steps that timeout.


##Solution##

The problem is likely related to your test list settings. There's a setting called UnexpectedDialogAction which allows the tests (in a test list) to automatically handle dialogs that are deemed "unexpected." Since it's hard to distinguish between expected and unexpected dialogs, this feature handle dialogs that it shouldn't. Here's how to determine whether this is the problem you're experiencing:


Execute the problematic test as part of a test list, and then by Quick Execution. If a dialog handling problem only exists in test list execution, change the **UnexpectedDialogAction** setting:

* **HandleAndFailTest** - Your test fails as soon as a dialog appears. This is the default mode. This can cause unexpected failures since the feature might not be able to correctly determine whether a dialog was expected.

* **HandleAndContinue** - This handles dialogs and allows the test to continue running. This can lead to problems because in this mode, a dialog may be handled before its corresponding dialog handling step. If your test contains a dialog handler step, it will timeout if the *HandleAndContinue* mode handles the dialog first.

* **DoNotHandle** - No dialogs are automatically handled. Dialog handler steps must be in the proper place in your test where you expect a dialog to appear.

If you determine that the UnexpectedDialogAction is causing unpredictable behavior in your test lists, set it *DoNotHandle* and the problem should disappear.

###Standalone version###

In Test Studio Standalone version, set the *UnexpectedDialogAction* from the *Edit Test List Settings menu*:

![UnexpectedDialogAction][1]

###Visual Studio plugin###

In the Visual Studio plugin, edit the <a href="/features/test-runners/MSTest" target="_blank">.testsettings</a> file that corresponds to the test list run:

![UnexpectedDialogAction Visual Studio][2]

[1]: /img/knowledge-base/dialogs-and-popups-kb/unexpected-dialog-action/fig1.png
[2]: /img/knowledge-base/dialogs-and-popups-kb/unexpected-dialog-action/fig2.png
