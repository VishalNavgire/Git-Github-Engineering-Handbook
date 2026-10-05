# 🌳 The Three-State Architecture

*(Building on the `.git` directory concept from [04-Git-Repository](04-Git-Repository.md))*

Git does not simply "save" files. It moves file states across three distinct local environments. Understanding this flow is the key to mastering Git.

### 1. The Working Tree (The Sandbox)
*   **What it is:** The actual files you see and edit on your computer's disk.
*   **State:** Untracked or Modified.
*   **Safety:** 🔴 Volatile. Uncommitted changes deleted here are lost forever.

### 2. The Staging Area / Index (The Loading Dock)
*   **What it is:** A hidden file inside `.git/index` that queues up exactly what will go into your next commit.
*   **State:** Staged.
*   **Purpose:** Allows you to bundle related changes together before saving.

### 3. The Local Repository (The Vault)
*   **What it is:** The `.git/objects` database where Git permanently stores data.
*   **State:** Committed.
*   **Safety:** 🟢 Secure. Once data reaches here, it is nearly impossible to lose.

### The Flow of Data
```text
[Working Tree] ──────> [Staging Area] ──────> [Local Repository]
 (Edit files)   git add    (Queue)    git commit   (Saved forever)