# 🌿 Branches

*(Requires understanding of Commits from [07-Git-Objects](07-Git-Objects.md))*

In many older version control systems, creating a branch meant physically copying all files into a new folder. 

In Git, **a branch is simply a lightweight, movable pointer to a commit.**

### How Branches Work
A branch is literally just a tiny text file located in `.git/refs/heads/`. This text file contains nothing but the 40-character hash of a commit.

*   Creating a new branch is instantaneous. Git just creates a new text file.
*   When you make a new commit on a branch, the pointer automatically moves forward to point to the newest commit.

### Visualizing Branches
```text
          [feature-branch] ──┐
                             ▼
Commit A <── Commit B <── Commit C
                    ▲
          [main] ───┘