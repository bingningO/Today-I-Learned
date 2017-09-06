# Git Command: Cherry Pick

not familar with cherry pick so searched it.

always *git log* firstly to confirm the commits of **B branch** and then checkout **A branch** to cherry pick commits in **B** to **A**.

here is some use examples:

* normal pick from the first commit
```
git cherry-pick B~0
```

* pick by commit ID
```
git cherry-pick c91bb1c20d451fd6f1a45cced06447f9dfb938f4
```

* pick three commits
```
git cherry-pick B~0
git cherry-pick B~1
git cherry-pick B~2
```

* only pick content of the commit
```
git cherry-pick B~0 -n
```
