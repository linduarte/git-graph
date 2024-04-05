# Learning Git  - A Hands-On and Visual Guide to the Basics of Git

---
title: Rainbow repo

---

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchOrder': 0}} }%%


gitGraph LR:
    commit id:"red"
    commit id:"orange"
    branch feature
    commit id:"yellow"
    merge main

```

$ git hist  

b0612f2 2024-03-22 Charles Duarte (HEAD -> feature) yellow  

923bb68 2024-03-22 Charles Duarte (main) orange  

12a73ff 2024-03-22 Charles Duarte red

Os hashs (b0612f2...) foram alterados pelas cores nas mensagens de 'commit'.
