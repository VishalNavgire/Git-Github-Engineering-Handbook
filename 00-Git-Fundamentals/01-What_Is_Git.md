# What Is Git?

> **Git is a distributed version control system that records the history of changes to a project, allowing you to track, compare, collaborate, experiment, and recover work safely.**

Git is one of the most widely used version control systems in software engineering. It is used to manage everything from small personal projects to large enterprise codebases.

However, understanding Git is more than memorizing commands such as `git add`, `git commit`, and `git push`.

To use Git effectively, you first need to understand **what problem Git solves, how Git thinks about changes, and how it maintains the history of a project.**

This chapter establishes those fundamentals.

---

## 1. What Problem Does Git Solve?

Consider a project that is being changed continuously.

You may start with:

```text
project-v1
```

Then make several changes:

```text
project-v2
project-v3
project-v4
```

Without version control, people often resort to manually creating copies:

```text
Project/
Project-Backup/
Project-Final/
Project-Final-New/
Project-Final-New-Updated/
Project-Final-New-Updated-2/
```

This approach quickly becomes difficult to manage.

You may not know:

* What changed between two versions?
* Who made a particular change?
* When was the change introduced?
* Why was it made?
* Which version was working?
* Can an earlier version be restored?
* What happens if two people modify the same file?
* How can multiple developers work on different features at the same time?

Git addresses these problems by maintaining a **structured history of changes**.

---

# 2. What Is Version Control?

**Version control** is a system for recording and managing changes to files over time.

A version control system allows you to maintain a history such as:

```text
Version 1
   ↓
Version 2
   ↓
Version 3
   ↓
Version 4
```

Instead of relying on manually created copies, the system maintains relationships between versions.

This makes it possible to:

* Track changes
* Compare versions
* Identify when changes were introduced
* Identify who made changes
* Create separate lines of development
* Combine changes from different developers
* Restore previous versions
* Investigate problems
* Collaborate safely

Git is a **distributed version control system (DVCS)**.

---

# 3. What Does "Distributed" Mean?

Traditional centralized version control systems generally depend on a central server for the primary repository.

Git uses a different model.

A Git repository can exist **locally on your computer with its complete history**.

For example:

```text
                 Git Repository
                       │
             ┌─────────┴─────────┐
             │                   │
        Developer A          Developer B
        Repository           Repository
             │                   │
             └─────────┬─────────┘
                       │
                 Remote Repository
```

Each developer can have a complete local Git repository.

This means many Git operations can be performed without a network connection.

For example, you can generally:

* Create commits
* Inspect history
* Create branches
* Compare changes
* Switch branches
* Experiment with changes

without needing GitHub or another remote server.

The remote repository becomes important when you want to **share or synchronize changes** with other repositories.

---

# 4. Git Is Not GitHub

One of the most important distinctions for beginners is:

> **Git and GitHub are not the same thing.**

### Git

Git is the **version control system**.

It provides capabilities such as:

* Tracking changes
* Creating commits
* Managing branches
* Maintaining history
* Comparing changes
* Merging changes
* Rebasing
* Recovering previous states

### GitHub

GitHub is a **platform built around Git repositories**.

It provides capabilities such as:

* Hosting Git repositories
* Pull Requests
* Code review
* Issues
* Repository permissions
* Collaboration
* GitHub Actions
* Project management features

A useful mental model is:

```text
Git
│
├── Version Control
├── Commits
├── Branches
├── History
├── Merge
├── Rebase
└── Local Repository
        │
        │ Synchronization
        ▼
     GitHub
        │
        ├── Remote Repository
        ├── Pull Requests
        ├── Code Review
        ├── Issues
        └── GitHub Actions
```

You can use **Git without GitHub**.

GitHub is one of many platforms that can host and collaborate around Git repositories.

---

# 5. Git Thinks in History, Not Just Files

A common beginner mental model is:

> "Git stores copies of my files."

That is not the best way to think about Git.

A better mental model is:

> **Git records the state of a project at particular points in its history and connects those states together.**

For example:

```text
        Commit A
           │
           ▼
        Commit B
           │
           ▼
        Commit C
           │
           ▼
        Commit D
```

Each commit represents a recorded state of the project along with metadata describing that commit.

The history allows Git to answer questions such as:

* What changed?
* When did it change?
* Who made the change?
* What was the project like before the change?
* What commits came before this one?
* Which branch contains this change?

This history is one of Git's most powerful characteristics.

---

# 6. What Is a Commit?

A **commit** is a recorded point in the history of a Git repository.

You can think of a commit as:

> **A named point in the project's history representing a particular state of the tracked content, together with information about the change and its place in history.**

A commit contains information such as:

* The identity of the author
* Commit timestamp
* Commit message
* A unique commit identifier
* Relationship to previous commit(s)
* The recorded project state

A simplified history might look like:

```text
A ── B ── C ── D
              ▲
          latest commit
```

Commit `D` has a relationship with `C`.

`C` has a relationship with `B`.

`B` has a relationship with `A`.

This connected history is what allows Git to move through the project's development timeline.

---

# 7. Git Tracks Changes Through Commits

Suppose a developer creates a simple project:

```text
project/
└── README.md
```

The initial state is committed:

```text
Commit A
```

Later, the developer modifies `README.md`:

```text
project/
└── README.md    ← modified
```

Git can identify that the current working state differs from the previously recorded state.

The developer can then record another commit:

```text
Commit A ── Commit B
```

The repository now has a history.

Later:

```text
Commit A ── Commit B ── Commit C ── Commit D
```

This history becomes the foundation for:

* Auditing changes
* Comparing versions
* Troubleshooting
* Collaboration
* Branching
* Recovery

---

# 8. Git Allows Multiple Lines of Development

Projects rarely develop in a perfectly straight line.

For example, a team may have a primary development line:

```text
A ── B ── C ── D
```

A developer may need to experiment with a new feature without immediately changing the primary line.

Git allows another line of development:

```text
             E ── F
            /
A ── B ── C ── D
```

This concept is called a **branch**.

Branches allow developers to:

* Develop features independently
* Experiment safely
* Fix bugs separately
* Work on multiple tasks simultaneously
* Review changes before integrating them

Branches become much more important later in this Handbook.

See:

```text
08-Branches.md
```

---

# 9. Git Enables Collaboration

Git can be used by a single developer, but it becomes especially powerful when multiple people work on the same project.

Consider two developers:

```text
                 Shared Project
                      │
             ┌────────┴────────┐
             │                 │
        Developer A       Developer B
             │                 │
        Feature A          Feature B
             │                 │
             └────────┬────────┘
                      │
                   Integrate
                      │
                      ▼
               Shared History
```

Each developer can work on their own branch, record commits, and eventually integrate their work.

Git provides the mechanisms for managing these different lines of development.

Platforms such as GitHub add collaboration workflows around those Git capabilities.

---

# 10. Git Is Also a Recovery Mechanism

Version control is not only about collaboration.

It can also provide valuable recovery capabilities.

Because Git maintains history, you can often investigate earlier states of a project.

For example:

```text
Current
   │
   ▼
Commit D
   │
   ▼
Commit C
   │
   ▼
Commit B
   │
   ▼
Commit A
```

If something goes wrong in the current state, the previous history may provide evidence about:

* What changed
* When it changed
* What the project looked like previously
* Which commit introduced a problem
* Whether previous work can be restored

This is why understanding Git's internal state becomes extremely important when troubleshooting.

Later sections of this Handbook will build on this foundation.

---

# 11. Git's Core Areas

A Git workflow can be simplified into three major areas:

```text
┌─────────────────────┐
│     Working Tree    │
│                     │
│  Your current files │
└──────────┬──────────┘
           │
        git add
           │
           ▼
┌─────────────────────┐
│    Staging Area     │
│       (Index)       │
│                     │
│ Changes selected    │
│ for next commit     │
└──────────┬──────────┘
           │
       git commit
           │
           ▼
┌─────────────────────┐
│      Repository     │
│                     │
│  Commit history     │
└─────────────────────┘
```

This model is fundamental to understanding Git.

We will examine these areas in detail in:

```text
05-Working-Tree-Staging-Area-Repository.md
```

---

# 12. Git's Basic Workflow

At a high level, a typical Git workflow looks like this:

```text
Make a change
      │
      ▼
Working Tree
      │
      │ git add
      ▼
Staging Area
      │
      │ git commit
      ▼
Local Repository
      │
      │ git push
      ▼
Remote Repository
```

When working with a remote repository, changes may also flow in the opposite direction:

```text
Remote Repository
      │
      │ fetch / pull
      ▼
Local Repository
      │
      ▼
Working Tree
```

The exact behavior of these commands will be covered later.

At this stage, the important thing is to understand the **movement of changes between Git's major areas**.

---

# 13. Why Git Is Powerful for Troubleshooting

Git's history provides something extremely valuable during troubleshooting:

> **Evidence.**

Suppose an application worked yesterday but fails today.

Without version control, you might ask:

> "What changed?"

With Git, you can investigate the project's history:

```text
Known-good state
       │
       ▼
Commit A
       │
       ▼
Commit B
       │
       ▼
Commit C
       │
       ▼
Commit D
       │
       ▼
Current problem
```

You can then investigate:

* Which commits occurred between the known-good and problematic states?
* Which files changed?
* Who made the changes?
* Which commit introduced the behavior?
* Can the change be reproduced?
* Can the previous state be restored or used as a reference?

This is one reason Git is more than a source-code storage mechanism.

It is also an **investigation and recovery tool**.

---

# 14. Git and the Engineering Troubleshooting Mindset

Throughout this Handbook, Git troubleshooting will follow an evidence-first approach:

```text
Symptom
   ↓
Evidence
   ↓
Analysis
   ↓
Root Cause
   ↓
Remediation
   ↓
Verification
```

For example:

```text
Symptom
"Why is my branch different from the remote?"
          ↓
Evidence
Inspect repository and branch state
          ↓
Analysis
Determine local/remote relationship
          ↓
Root Cause
Local branch is behind / ahead / diverged
          ↓
Remediation
Choose the appropriate synchronization strategy
          ↓
Verification
Confirm expected branch state
```

The goal is not to immediately run commands until something appears to work.

The goal is to:

> **Understand the state before changing the state.**

This principle will become increasingly important as we move into advanced workflows and recovery scenarios.

---

# 15. What Git Is Not

It is useful to establish a few boundaries.

### Git is not a backup system

Git can provide powerful recovery capabilities, but a Git repository should not automatically be treated as a complete backup strategy.

A repository can be deleted, corrupted, misconfigured, or incorrectly manipulated.

Important projects should have appropriate backup and recovery mechanisms.

### Git is not a deployment platform

Git can participate in deployment workflows, but Git itself does not deploy applications.

CI/CD platforms such as GitHub Actions can consume Git repositories and automate builds, tests, and deployments.

### Git is not GitHub

Git is the version control system.

GitHub is a platform that provides hosting and collaboration capabilities around Git repositories.

### Git does not automatically understand your intent

Git records and manipulates repository state based on the operations you perform.

It cannot determine that:

> "This commit was accidental, so I should probably undo it."

Understanding the state and choosing the appropriate operation remains the engineer's responsibility.

---

# 16. Key Git Concepts Introduced

By the end of this chapter, you should recognize the following terms:

| Concept                  | Meaning                                                        |
| ------------------------ | -------------------------------------------------------------- |
| **Git**                  | Distributed version control system                             |
| **Repository**           | Git-managed project and its history                            |
| **Working Tree**         | Current files being worked on                                  |
| **Staging Area / Index** | Changes selected for the next commit                           |
| **Commit**               | Recorded point in repository history                           |
| **Commit History**       | Connected sequence of repository states                        |
| **Branch**               | Movable reference used to represent a line of development      |
| **HEAD**                 | Reference indicating the currently checked-out position        |
| **Remote**               | Another repository used for synchronization                    |
| **GitHub**               | Platform for hosting and collaborating around Git repositories |

These concepts will be expanded throughout the following chapters.

---

## Core Principle

> **Don't start by memorizing Git commands. Start by understanding Git's state and history.**

Once the mental model is clear, the commands become much easier to understand, troubleshoot, and use safely.
