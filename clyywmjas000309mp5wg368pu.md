---
title: "Types of Version Control System (Cvcs && Dvcs)"
datePublished: Tue Jul 23 2024 21:04:54 GMT+0000 (Coordinated Universal Time)
cuid: clyywmjas000309mp5wg368pu
slug: types-of-version-control-system
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1721738266748/852f7621-3495-4b6a-b536-774b96eeb635.png
tags: mercurial, git, vcs, dvcs, docs, pros-and-cons, 2articles1week, perforce

---

### **Centralized Versioned Control System**

In centralized source control system there is a main server where all versions of the code are stored. To start working on a project users first bring code from this central server to their local machines. This process is similar to getting an update from the main repository for the current version of the code on our own system. Once we have the latest code we can make our changes on it. Later we push those changes back to the central repository which means we're merging our code into the main repository or creating a new version of the code. Everything is managed centrally in this model with a repository containing all versions and branches of the code. The workflow is to fetch the latest code making our necessary changes and then commit or merge those changes back to the place where others can access them.

**Popular CVCS Tools : 1.** Subversion **2\.** HelixCore

### **Distributed Version Control System**

In distributed version control system each developer has their own copy of the entire code history and all its branches on their local machine. This setup is more flexible than centralized control because developers can work independently and offline. When starting a project, we clone the code from the original repository to our local drive. After making changes locally we will commit those changes to our local repository. The local repository stores our changes separately until we synchronize with the main repository by pulling new changes or pushing our changes. This approach allows more autonomy and flexible collaboration between developers before integrating changes into the main repository.

**Popular DVCS Tools : 1.** Perforce **2\.** mercurial **3.** git

### Difference between (Pros & Cons) CVCS & DVCS

**CVCS :** It is easier for beginners than dvcs. In this system developers work with a single central server where they are manage their code versions by their own. It's easy to learn and set up because developers only need to remember commands for basic operations like checking out code, making changes and sending them back to where they belong.

**Internet Dependency :** Each steps in cvcs requires a proper Internet connection (checking out, committing, updating).

**No local history :** Developers only have a working copy of the code on their local drive. The complete version history is stored on the central server.

**Slow operations :** Making changes and retrieving history is slow because these operations involve communication over the Internet.

**Large files :** Suitable for storing large binary files as only the latest version needs to be downloaded or uploaded, not the entire history.

**Commit independence :** The speed of operation is not significantly affected by the number of commits in the project's history.

**DVCS :** In a dvcs like Git developers work on branches effortlessly because they have the entire code history in locally. This allows them to branch, switch and merge on their own machines before syncing with the central repository. Centralized systems, such as SVN, are often slower and involve more complex processes, as they require direct server communication for branch and merge operations, which can hinder collaborative development.

**Offline work :** Developers can perform most operations (like making changes, viewing history) without the need for an internet connection.

**Complete History Locally :** Each developer maintains a complete history of the project on their local hard drive, allowing for independence and flexibility.

**Speed :** Making changes and retrieving history is faster because operations are performed locally rather than over a network.

**Binary files :** Not ideal for large binary files due to the increase in repository size with each commit, which can slow down operations.

**Download time :** Projects with many commits can take significant time to download all changes, especially if the project history is extensive.