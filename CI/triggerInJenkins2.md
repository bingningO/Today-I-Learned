# Trigger In Jenkins 2.0

two way to trigger.

1. set *trigger time* and *trigger intervals* in settings, and can use **^$release.$** to set auto-trigger for all branches besides release branch.
2. set in Jenkinsfile such as 

```
trigger 
```

and in the codes above, SCMPolling is a little complex to me, so I copy some strategies as following:

```
// at 11am, 16pm every day 
0 11, 16 * * *
```
