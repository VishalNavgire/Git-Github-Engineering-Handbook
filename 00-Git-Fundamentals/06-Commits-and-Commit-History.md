# 📸 Commits and Commit History

*(Requires understanding of the Local Repository from [05-Working-Tree-Staging-Area-Repository](05-Working-Tree-Staging-Area-Repository.md))*

A commit is often misunderstood as a "diff" or a "patch" (a record of what changed). **This is false.**

### What is a Commit?
A commit is a **complete, standalone snapshot** of your entire project at an exact point in time. 

If a file didn't change between commits, Git doesn't save it again; it just creates a link to the previous identical version.

### The Anatomy of a Commit
Every commit contains:
1.  **A Unique ID:** A 40-character cryptographic hash (e.g., `a1b2c3d4...`).
2.  **Metadata:** The Author name, email, and timestamp.
3.  **A Message:** The human-readable description of *why* the snapshot was taken.
4.  **A Parent Pointer:** A link to the commit(s) that came immediately before it.

### The History Chain
Because every commit points to its parent, they form an unbreakable chain of history:
```text
Commit A (Parent) <── Commit B <── Commit C (Latest)