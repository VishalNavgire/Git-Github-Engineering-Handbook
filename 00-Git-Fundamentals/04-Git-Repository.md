# Git Repository

A **Git repository** is the data structure Git uses to store and manage a project's version history.

A typical working repository looks like:

```text
MyProject/
│
├── Project Files
│
└── .git/
    ├── objects/
    ├── refs/
    ├── HEAD
    ├── index
    └── config

The important distinction is:

Working Tree
    │
    │ stage changes
    ▼
Staging Area
    │
    │ commit
    ▼
Git Repository

The working tree contains the files you work on.

The staging area represents what you intend to include in the next commit.

The repository stores Git's history, objects, references, and metadata.

What Is Stored in .git?

You do not need to memorize every file inside .git. Understand the major components:

Component	Purpose
HEAD	Identifies the current checkout position
index	Represents the staging area
objects/	Stores Git objects such as commits, trees and blobs
refs/	Stores references such as branches and tags
config	Repository-specific configuration
logs/	Records reference movements when reflogs are available

Think of .git as Git's internal database and metadata area.

Do not modify or delete .git casually.

Git Repository vs Project Folder

A project folder and a Git repository are related, but they are not the same thing.

Project Folder
│
├── README.md
├── app.py
├── config.json
│
└── .git/       ← Git repository data

If .git is removed, the project files may still exist, but the directory no longer has the same local Git history and repository metadata.

Git Objects

Git stores history using objects.

Git Objects
│
├── Commit  → History / metadata
├── Tree    → Directory structure
├── Blob    → File content
└── Tag     → Annotated reference

These objects are connected to represent different states of a project over time.

Detailed object behavior is covered separately in:

07-Git-Objects.md

References

Git uses references to identify important objects.

Common references include:

Branch
Tag
HEAD
Remote-tracking branch

For example:

main ──► Commit C ──► Commit B ──► Commit A

The branch does not contain a separate copy of the project.

It points to a commit in the repository's history.

Local and Remote Repositories

A Git repository can exist entirely on your computer:

Local Repository

It can also be connected to another repository:

Local Repository
       │
       │ push / fetch
       ▼
Remote Repository

The local and remote repositories maintain their own states.

For example:

Local:  main → Commit D
Remote: main → Commit C

The local branch is now ahead of the remote branch.

This distinction becomes important when working with:

fetch
pull
push
Tracking branches
Diverged branches

These topics are covered later in the Handbook.

Repository State

A repository can be in many different states:

Clean
Modified
Staged
Untracked
Ahead
Behind
Diverged
Conflicted
Merge in progress
Rebase in progress
Detached HEAD

Therefore, when troubleshooting Git, don't immediately ask:

"Which command should I run?"

First ask:

"What state is the repository currently in?"

This is the foundation of the Handbook's troubleshooting approach:

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
Repository Mental Model

Keep this simple model in mind:

                 Git Repository
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       Objects      References    Metadata
          │            │
          │            ├── Branches
          │            ├── Tags
          │            └── HEAD
          │
          ├── Commits
          ├── Trees
          └── Blobs

And the everyday workflow:

Working Tree
      │
      │ git add
      ▼
Staging Area
      │
      │ git commit
      ▼
Repository
Troubleshooting Checklist

When something unexpected happens, establish the repository context first:

Which repository am I in?
What is the current branch?
Where is HEAD pointing?
Are there working-tree changes?
Are changes staged?
What is the recent history?
Is a remote involved?
Is the repository ahead, behind or diverged?

Only then decide what action to take.

Key Takeaways
A Git repository stores project history and Git metadata.
.git contains the repository's internal data.
The working tree, staging area and repository represent different states.
Git stores history using objects such as commits, trees and blobs.
Branches and tags are references to Git objects.
Local and remote repositories can have different states.
Repository state should be understood before taking corrective action.
.git should not be modified or deleted casually.

Understand the repository state before changing it.