# New GitHub Flow (deploy at release)

the [new Github flow](https://guides.github.com/introduction/flow/) says deploying before merging into **Master** branch.

In fact delopying at **release** branch or deploying after merging into **Master** branch are the same. 

In my opinion, the new change thinks about:
1. The tests on **Release** is enough to make sure its deployable, which's more safety Just in case there might has some changes in **Master**.
2. If the Deploy on **Release** has bugs, developers can directly roll back to the current **Master** commit, which is very fast.

And after confirmation of deploying on **Release**, developers merge it into **Master**, making commits on **Master** are always productable.
