# Priority

{% hint style="info" %}
There is a concept of **priority** among the command trees of the **formula repositories**. 

This makes it possible to **avoid repetitive commands** after joining the trees of all commands by the CLI.
{% endhint %}

Here is the **default priority** defined in the CLI among the repositories:

* Priority 0: Core 
* Priority 1: Location 
* Priority 2: Other repositories

This rule allows each user \(_single_\) / organization \(team\) to define the priority among the other repositories.

## Example

It is possible for a user to choose between the 2 scenarios below:

![](https://lh4.googleusercontent.com/HjfbyCr7FUbOrhlx7uEqr7-fgjmVbivXPSk9X3CD92BPtF4sgy4ojBl4-HKAzAcI7OGacCGWVzMJCDPh_IfS8y3520_i-TwccY2PQEqrnXgrZKcSdBiOyEjBwzB1Uy9E1b3KQaPL)![](https://lh5.googleusercontent.com/Oc1HatluaibDzbcfd0N34oERi8al1zsJj6qB4XDNpueoP5xgizDIarZmQ2BoGCXFp0K-g5QnQC6-pn1eQFoO15QKmQEOklfJ_AdK7hN0EeHpK7T3HrIm_wN0G_rNcbN6LP7VFBDK)

### **Scenario 1**

Priority would be given to commons commands over your team's commands.

### S**cenario 2**

Priority would be given to team commands over commons commands. This would allow, for example, a user / team to use a command that is in the **ritchie-formulas** \(commons\) repository tree for a formula in their repository, performing a different operation with the same command, since it would have priority.

{% hint style="warning" %}
It is possible to configure the priority between the repositories in the **repo** folder of the [.rit folder](../cli/.rit-folder.md) where you have a configurable repositories.json file. 

For more information on how to manipulate [repositories](repository.md), check out the documentation here: Repository.
{% endhint %}

