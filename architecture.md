# Git Architecture Overview


Goal for git

- Support distributed workflows similar to those enabled by BitKeeper (collaborate)
- Offer safeguards against content corruption 
- Offer high performance



A Version Control System usually has three core functionalities, all of which Linus built into Git.   

- It must be able store content. 
- track changes to said content (all history including merge metadata),   
- optionally distribute the content and commit history with project collaborators. 


Git is essentially a content-addressable filesystem made up of objects that form a hierarchy which mirrors the content’s filesystem tree.

Each commit has the parent link 

## content storage 

Directed Acyclic Graph (DAG) or delta-based changeset ?


## Merge strategy 

### Fast-forward merge 

Master : A -- B -- C (Head)

Feature : A -- B -- C -- D -- E (Head)

Merged Master : A -- B -- C -- D -- E

Feature Branch has the latest commit of master , 
if Feature branch need merge to master , just point master head to feature branch head


### Three way merge

Master : A -- B -- C 

Feature : A -- B -- D -- E

Merged Master : A -- B -- C -- D -- E -- F 

Merge Feature to Master , user need to fix the conflict if any , the conflict will be submit as another commit(F) . And F has two parents (C/E) .



reference : https://medium.com/@willhayjr/the-architecture-and-history-of-git-a-distributed-version-control-system-62b17dd37742





