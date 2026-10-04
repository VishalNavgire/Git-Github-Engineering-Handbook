# Git vs GitHub

> **Git is a distributed version control system. GitHub is a platform that hosts Git repositories and provides collaboration, code review, automation, and other development services around them.**

Git and GitHub are closely related, but they are **not the same thing**.

This distinction is one of the first concepts anyone learning Git should understand.

A simple way to remember it is:

```text
Git       = Version Control
GitHub    = Collaboration Platform
```

Git provides the technology for tracking and managing changes.

GitHub provides a platform where Git repositories can be hosted, shared, reviewed, automated, and collaboratively managed.

---

# 1. The Short Answer

If you remember only one thing from this chapter, remember this:

> **Git can work without GitHub. GitHub cannot replace Git's version-control functionality.**

Git can run entirely on your local computer.

For example:

```text
Your Computer
│
└── project/
    └── .git/
```

You can create commits, branches, inspect history, compare changes, and perform many other Git operations without connecting to the internet.

GitHub becomes useful when you want to:

* Store a Git repository remotely
* Collaborate with other developers
* Review code
* Manage issues
* Automate workflows
* Control repository access
* Share projects
* Build CI/CD pipelines

---

# 2. What Is Git?

**Git is a distributed version control system (DVCS).**

Git's primary responsibility is managing the history and state of a project.

Git provides functionality for:

* Tracking changes
* Creating commits
* Maintaining history
* Creating branches
* Switching between branches
* Comparing changes
* Merging changes
* Rebasing
* Recovering previous states
* Synchronizing repositories

A simplified view is:

```text
                         Git
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
     History           Branches          Changes
        │                 │                 │
        ├── Commits       ├── Feature       ├── Working Tree
        ├── Parents       ├── Bug Fix       ├── Staging Area
        └── References    └── Main          └── Repository
```

Git itself does not require GitHub.

---

# 3. What Is GitHub?

**GitHub is a developer platform built around Git.**

GitHub provides a remote environment where Git repositories can be hosted and additional collaboration capabilities can be built around them.

GitHub provides features such as:

* Remote Git repositories
* Pull Requests
* Code review
* Issues
* Discussions
* Repository permissions
* Teams and organizations
* GitHub Actions
* Security features
* Releases
* Project management
* Developer collaboration

A simplified model is:

```text
                         GitHub
                            │
          ┌─────────────────┼──────────────────┐
          │                 │                  │
     Repositories      Collaboration       Automation
          │                 │                  │
          ├── Git repos     ├── PRs           ├── Actions
          ├── Branches      ├── Reviews       ├── CI/CD
          └── Releases      ├── Issues        └── Workflows
                            └── Discussions
```

GitHub uses Git repositories as one of its core building blocks.

---

# 4. Git and GitHub: Side-by-Side

| Capability                | Git                      | GitHub                                      |
| ------------------------- | ------------------------ | ------------------------------------------- |
| Version control           | ✅                        | Uses Git                                    |
| Create commits            | ✅                        | Provides interfaces around Git              |
| Branch management         | ✅                        | Provides Git-based branch management        |
| Local repository          | ✅                        | ❌                                           |
| Commit history            | ✅                        | Displays Git history                        |
| Merge                     | ✅                        | Supports merges through Git-based workflows |
| Rebase                    | ✅                        | Supports workflows involving rebase         |
| Remote repository hosting | ❌                        | ✅                                           |
| Pull Requests             | ❌                        | ✅                                           |
| Code review               | ❌                        | ✅                                           |
| Issues                    | ❌                        | ✅                                           |
| Discussions               | ❌                        | ✅                                           |
| Repository permissions    | Limited/local            | ✅                                           |
| GitHub Actions            | ❌                        | ✅                                           |
| CI/CD workflows           | Can integrate with tools | ✅ through Actions and integrations          |
| Collaboration platform    | ❌                        | ✅                                           |

The important distinction is:

> Git provides **version control capabilities**.
> GitHub provides **hosting and collaboration capabilities around Git repositories**.

---

# 5. Can I Use Git Without GitHub?

**Yes.**

This is one of the most important things to understand.

You can create a Git repository locally:

```text
Developer Computer
│
└── MyProject/
    │
    ├── application files
    ├── README.md
    └── .git/
```

You can then create commits and maintain history without using GitHub.

Conceptually:

```text
Working Tree
     │
     │ git add
     ▼
Staging Area
     │
     │ git commit
     ▼
Local Git Repository
```

No internet connection is required for many of these operations.

You could even use Git to manage:

* Personal scripts
* Documentation
* Configuration files
* Automation projects
* Infrastructure code
* Learning projects

without ever creating a GitHub repository.

---

# 6. Can I Use GitHub Without Understanding Git?

Technically, GitHub provides graphical and web-based interfaces that can hide some Git operations.

However, for serious development and troubleshooting, understanding Git itself is extremely important.

For example, GitHub may show:

```text
Your branch is behind the base branch.
```

or:

```text
This branch has conflicts that must be resolved.
```

Understanding what that means requires knowledge of Git concepts such as:

* Branches
* Commits
* Parents
* Merge
* Rebase
* Remote-tracking branches
* Repository state

Therefore:

> **GitHub makes Git easier to collaborate around, but it does not eliminate the need to understand Git.**

---

# 7. GitHub as a Remote Repository

One of the most common GitHub workflows looks like this:

```text
                    LOCAL MACHINE
                  ┌───────────────┐
                  │ Working Tree  │
                  └───────┬───────┘
                          │
                       git add
                          │
                          ▼
                  ┌───────────────┐
                  │ Staging Area  │
                  └───────┬───────┘
                          │
                      git commit
                          │
                          ▼
                  ┌───────────────┐
                  │ Local Git     │
                  │ Repository    │
                  └───────┬───────┘
                          │
                       git push
                          │
                          ▼
                  ┌───────────────┐
                  │    GitHub     │
                  │   Repository  │
                  └───────────────┘
```

Here:

* Git manages the local repository.
* GitHub hosts a remote copy of the repository.
* `git push` sends commits from the local repository to the remote repository.

This distinction becomes important when troubleshooting synchronization problems.

---

# 8. GitHub Is More Than Repository Hosting

It would be inaccurate to describe GitHub simply as:

> "A website where Git repositories are stored."

That describes only part of what GitHub provides.

A GitHub repository can become the center of a broader engineering workflow:

```text
                         GitHub Repository
                                │
        ┌───────────────────────┼───────────────────────┐
        │                       │                       │
     Source Code           Collaboration            Automation
        │                       │                       │
        │                   Pull Requests           Actions
        │                   Code Reviews             CI/CD
        │                   Issues
        │                   Discussions
        │
        └───────────────────────┬───────────────────────┘
                                │
                         Engineering Workflow
```

For example, a developer may:

1. Create a feature branch using Git.
2. Make changes locally.
3. Create commits.
4. Push the branch to GitHub.
5. Open a Pull Request.
6. Receive code review.
7. Run automated tests using GitHub Actions.
8. Merge the Pull Request.
9. Deploy the resulting application.

Git provides the version-control foundation.

GitHub provides many of the collaboration and automation capabilities surrounding it.

---

# 9. Git vs GitHub: A Practical Example

Imagine you are developing a PowerShell automation script.

Your local project might look like:

```text
PowerShell-Automation/
│
├── Scripts/
│   └── Get-SystemInfo.ps1
├── Tests/
│   └── Get-SystemInfo.Tests.ps1
├── README.md
└── .git/
```

Git tracks the project locally.

You might make a change:

```text
Get-SystemInfo.ps1
        │
        ▼
Modified
        │
        ▼
git add
        │
        ▼
Staged
        │
        ▼
git commit
        │
        ▼
Local Git History
```

You then push the commit:

```text
Local Repository
       │
       │ git push
       ▼
GitHub Repository
```

GitHub can then provide:

```text
GitHub Repository
       │
       ├── Pull Request
       ├── Code Review
       ├── Issue Tracking
       └── GitHub Actions
              │
              ├── Lint
              ├── Test
              └── Build
```

The Git repository is still the underlying version-control system.

---

# 10. GitHub Does Not Replace the Local Repository

A common misconception is:

> "My repository is on GitHub, so Git is no longer involved."

In reality, a typical developer workflow has multiple repository copies.

For example:

```text
                    Remote Repository
                    ┌───────────────┐
                    │    GitHub     │
                    └───────┬───────┘
                            │
                  fetch / pull / push
                            │
                            ▼
                    Local Repository
                    ┌───────────────┐
                    │      Git      │
                    └───────────────┘
```

Your local repository contains its own Git history.

The GitHub repository is another repository containing its own copy of the Git history.

Git provides the mechanisms for synchronizing them.

---

# 11. What Happens When You Clone a GitHub Repository?

Suppose a repository exists on GitHub:

```text
GitHub
└── MyProject
```

You run:

```bash
git clone <repository>
```

Conceptually, Git creates a local copy:

```text
GitHub
└── MyProject
        │
        │ clone
        ▼
Your Computer
└── MyProject
    ├── files
    └── .git/
```

Your local repository now contains Git metadata and history.

The local repository also remembers the remote repository from which it was cloned.

This remote is commonly named:

```text
origin
```

The meaning of `origin` will be explored in detail in the Remote Repositories section.

---

# 12. Local Repository vs Remote Repository

It is useful to distinguish these terms:

### Local Repository

The Git repository stored on your computer.

```text
Your Computer
└── project/
    └── .git/
```

### Remote Repository

Another Git repository that your local repository can synchronize with.

For example:

```text
GitHub
└── organization/project
```

The remote repository does not have to be hosted on GitHub.

Other platforms and self-hosted Git servers can also host Git repositories.

The relationship can therefore be represented as:

```text
             Local Git Repository
                       │
                       │
               Remote Repository
                       │
             ┌─────────┴─────────┐
             │                   │
          GitHub             Other Git host
```

---

# 13. GitHub Is Not the Only Git Hosting Platform

Git is independent of GitHub.

A Git repository can be hosted on many different platforms or servers.

Examples include:

* GitHub
* GitLab
* Bitbucket
* Azure Repos
* Self-hosted Git servers

The underlying version-control system remains Git.

This is an important architectural distinction:

```text
                Git
                 │
       ┌─────────┼─────────┐
       │         │         │
    GitHub     GitLab   Self-hosted
       │
       └── Collaboration / Hosting
```

Therefore, learning Git gives you skills that are transferable across different Git hosting platforms.

---

# 14. GitHub and Pull Requests

A **Pull Request (PR)** is a GitHub collaboration mechanism built around Git branches and commits.

A simplified workflow is:

```text
main
 │
 ├───────────────┐
 │               │
 ▼               ▼
Feature branch   main
 │
 ├── Commit A
 ├── Commit B
 └── Commit C
        │
        ▼
    Push to GitHub
        │
        ▼
 Pull Request
        │
        ▼
 Code Review
        │
        ▼
   Merge
        │
        ▼
      main
```

The Pull Request itself is a **GitHub feature**.

The branch and commits involved in that Pull Request are **Git concepts**.

This distinction becomes very important when troubleshooting Pull Requests.

---

# 15. GitHub Actions and Git

GitHub Actions extends the workflow into automation.

For example:

```text
Developer
   │
   │ git push
   ▼
GitHub Repository
   │
   │ trigger
   ▼
GitHub Actions
   │
   ├── Lint
   ├── Test
   ├── Build
   ├── Package
   └── Deploy
```

The repository's Git events can therefore become triggers for automated workflows.

For example:

```text
Push
  ↓
GitHub Actions
  ↓
PowerShell Tests
  ↓
Pester
  ↓
Build / Package
  ↓
Deployment
```

This is one of the reasons understanding Git becomes important for CI/CD engineering.

A failed workflow may actually originate from:

* Incorrect branch state
* Incorrect commit
* Missing file
* Incorrect repository path
* Authentication problem
* Merge conflict
* Workflow configuration
* Environment configuration

Later sections will connect Git troubleshooting with GitHub Actions troubleshooting.

---

# 16. Common Misconceptions

### Misconception 1

> **"Git and GitHub are the same thing."**

❌ Incorrect.

Git is the version control system.

GitHub is a platform built around Git.

---

### Misconception 2

> **"I need GitHub to use Git."**

❌ Incorrect.

Git can be used completely locally.

---

### Misconception 3

> **"GitHub is the Git server."**

⚠️ Not exactly.

GitHub is one platform that hosts Git repositories and provides additional services.

Git itself is not owned by or dependent on GitHub.

---

### Misconception 4

> **"A GitHub repository is just a folder containing files."**

❌ Incomplete.

A GitHub repository represents a Git repository hosted on GitHub, along with additional GitHub-specific metadata and collaboration capabilities.

---

### Misconception 5

> **"Pull Request is a Git command."**

❌ Incorrect.

A Pull Request is a GitHub collaboration feature.

Git provides branches, commits, merges, and other underlying version-control mechanisms.

---

### Misconception 6

> **"GitHub stores all my local Git state."**

❌ Incorrect.

Your local repository maintains its own Git state and history.

GitHub hosts a remote repository.

---

# 17. Why This Distinction Matters for Troubleshooting

This distinction becomes especially important when diagnosing problems.

Consider the statement:

> "My GitHub repository is broken."

That statement is too broad.

The actual problem could be:

```text
                    Problem
                       │
        ┌──────────────┼──────────────┐
        │              │              │
       Git          Network        GitHub
        │              │              │
   Local state     Connectivity    PR / Actions
   Branch          Authentication  Permissions
   Commit          Remote access   Workflow
   Rebase          Push/Pull       Settings
```

The first troubleshooting question should therefore often be:

> **Where does the problem actually exist?**

Is it:

* Your local Git repository?
* The remote repository?
* The network connection?
* Authentication?
* GitHub permissions?
* A Pull Request?
* GitHub Actions?
* Something else?

This is the beginning of **evidence-first troubleshooting**.

---

# 18. Git vs GitHub: Decision Guide

| If you want to...                   | Primarily think about                       |
| ----------------------------------- | ------------------------------------------- |
| Track changes locally               | **Git**                                     |
| Create commits                      | **Git**                                     |
| Create branches                     | **Git**                                     |
| Inspect history                     | **Git**                                     |
| Compare changes                     | **Git**                                     |
| Merge branches                      | **Git**                                     |
| Rebase                              | **Git**                                     |
| Recover commits                     | **Git**                                     |
| Host a repository online            | **GitHub**                                  |
| Collaborate with a team             | **GitHub + Git**                            |
| Create Pull Requests                | **GitHub + Git branches**                   |
| Review code                         | **GitHub**                                  |
| Track issues                        | **GitHub**                                  |
| Run GitHub Actions                  | **GitHub**                                  |
| Build CI/CD workflows               | **GitHub Actions + Git**                    |
| Troubleshoot local repository state | **Git**                                     |
| Troubleshoot PR mergeability        | **Git + GitHub**                            |
| Troubleshoot Actions failures       | **GitHub Actions + Git + repository state** |


---

## Core Principle

> **Git manages your version history. GitHub provides a platform for hosting, collaborating around, and automating workflows based on that Git history.**
