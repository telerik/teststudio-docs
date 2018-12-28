---
title: Condition
page_title: Condition
description: "Progress® Test Studio® for APIs - Condition"
position: 0
publish: true
---

# Condition

## Overview

The Condition is a special <a href="/features/verifications">Verification</a>, that specifies whether to execute a Test Step, or not. As oposed to the normal Verifications, the Condition does not Fail the Step, just prevents the Runtime from executing it.

> See <a href="/features/verifications">Verifications</a> for details how to configure the properties of the Condition.

![Condition][1]

Conditions have a prefix `[Condition]` in the Output window and in the `Telerik.ApiTesting.Runner.exe` console output. The result of a condition can be either TRUE or FALSE. 

![Condition][2]

![Condition][3]

> <a href="/features/verifications">Verifications</a> don't have a prefix in the Output window nor in the `Telerik.ApiTesting.Runner.exe` console output. 

## Usages

* When initializing a Test Run
* Skip <a href="/features/steps/verification">Verifications</a> on specific test environments
* Create a Loop with a <a href="/features/steps/goto">Goto</a> Step.



[1]: /img/features/condition.png
[2]: /img/features/condition-prefix.png
[3]: /img/features/condition-prefix-cmd.png



