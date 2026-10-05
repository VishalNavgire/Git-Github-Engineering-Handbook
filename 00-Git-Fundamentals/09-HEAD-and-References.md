# 📍 HEAD and References

*(Building on the concept of Branches from [08-Branches](08-Branches.md))*

If you have multiple branches pointing to different commits, how does Git know which files to load into your Working Tree? 

### The `HEAD` Pointer
`HEAD` is the **"You Are Here"** marker on the Git map. It is a special pointer that tracks what you currently have checked out.

*   **Attached State:** Normally, `HEAD` points to a *branch name* (e.g., `main`). If you make a commit, the branch moves forward, and `HEAD` moves with it.
*   **Detached State:** If you use Git to jump directly to a specific commit hash (instead of a branch name), `HEAD` disconnects from the branch. This is called a **Detached HEAD**.

### Visualizing HEAD
```text
  HEAD (You are here)
   │
   ▼
[main branch]
   │
   ▼
Commit B