# 🌍 Local Vs. Remote Repositories

*(Expanding beyond the local `.git` concepts established in [04-Git-Repository](04-Git-Repository.md))*

Git is a **Distributed Version Control System (DVCS)**. This means there is no central server required to use Git. Every developer has a full, 100% complete backup of the entire repository history on their local machine.

### 1. Local Repository
*   Lives on your computer.
*   You can create branches, stage files, and make commits entirely offline.

### 2. Remote Repository
*   Lives on the internet or a network server (e.g., GitHub, GitLab).
*   Used purely to sync your local history with your team's local histories.
*   The default name for the primary remote repository is traditionally called **`origin`**.

### Remote-Tracking Branches
When you connect to a remote repository, Git keeps local bookmarks of where the remote branches were the last time you checked. These look like `origin/main`.