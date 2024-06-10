<!--markdownlint-disable MD041-->
## Review the book "Learning Git" using 'Gitgraph" to represent repositories chapter by chapter with git commands

---

title: Chapter 4

---

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchOrder': 0}} }%%

gitGraph TB:

    commit id:"red"
   
```

---

title: Chapter 5

---

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchOrder': 0}} }%%

gitGraph TB:

    commit id:"red"
    commit id:"orange"
    branch feature
    commit id:"yellow"
    

```

---

title: Chapter 6

---

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchOrder': 0}} }%%

gitGraph TB:

    commit id:"red"
    commit id:"orange"
    branch feature
    commit id:"yellow"
    checkout main
    merge feature



```
